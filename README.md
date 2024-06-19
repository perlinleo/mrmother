# Running with a custom config

## Step 1: Edit config.yml

```yaml
schedule:
  TIMEZONE: 'Europe/Moscow'
  check:
    time:
      - '07:00'
      - '10:00'
      - '12:30'
    every:
      - 'monday'
      - 'tuesday'
      - 'wednesday'
      - 'thursday'
      - 'friday'
  daily:
    time:
      - '13:00'
    every:
      - 'monday'
      - 'tuesday'
      - 'wednesday'
      - 'thursday'
github:
  owner: 'qral-scan'
  repo: 'usb'
developer:
  chat_id: ''
  developers:
      - '@perlinleo' : '@lperlin'
```

## Step 2: Build docker container

build
```fish
    docker build -t telegram-ios-bot .
```

## Step 3: Add API tokens and chat_id to env.list file

```
telegram_token=<TELEGRAM_BOT_TOKEN>
telegram_group_chat_id=<TELEGRAM_GROUP_CHAT_ID>
github_token=<GITHUB_TOKEN>
```

## Step 4: Run container

start
```fish
    docker run --env-file=env.list -i telegram-ios-bot
```
