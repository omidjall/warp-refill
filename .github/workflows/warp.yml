name: Warp+ Auto Refill

on:
  schedule:
    - cron: '0 */6 * * *'  # هر 6 ساعت یک‌بار اجرا
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Run Warp+ Script
        run: |
          sudo apt update
          sudo apt install curl -y
          LICENSE_KEY="3Q40O5Dk-5yD4w89u-25l93BiJ"
          while true; do
            curl -s -X POST "https://api.cloudflareclient.com/v0a745/reg" \
            -H "Content-Type: application/json" \
            --data "{\"key\":\"$LICENSE_KEY\",\"install_id\":\"$(cat /proc/sys/kernel/random/uuid)\",\"fcm_token\":\"\",\"tos\":\"$(date -u +%Y-%m-%dT%H:%M:%S.%3NZ)\",\"type\":\"Android\",\"locale\":\"en_US\"}"
            echo "✔ شارژ شد. منتظر اجرای بعدی..."
            break
          done
