---
name: daily-stock-report
description: 매일 8시/20시 한국·미국 증시 리포트를 Slack으로 발송
model: claude-haiku-4-5-20251001
---

## 목표
한국경제 사이트(markets.hankyung.com)에서 한국·미국 증시 데이터를 수집해 Slack 채널로 리포트를 발송한다.

## 실행 순서

### 1단계: 한국경제에서 데이터 수집 (Claude for Chrome 사용)
- Claude for Chrome MCP(`mcp__Claude_in_Chrome__*`)를 사용해 `https://markets.hankyung.com/` 접속
- tabs_context_mcp(createIfEmpty: true)로 탭 확보 후 navigate
- 시장종합 페이지에서 다음 데이터를 screenshot·scroll로 수집:
  - 코스피 지수, 등락률, 개인/외국인/기관/프로그램 수급
  - 코스닥 지수, 등락률, 수급
  - KOSPI200 지수, 등락률, 수급
  - 종목 현황 (상한/상승/보합/하락/하한 수)
  - 글로벌 마켓: S&P500, 나스닥, 다우존스, 필라델피아 반도체, 독일DAX, 영국FTSE
- 뉴스 탭(`https://www.hankyung.com/koreamarket/news/all-news`)으로 이동해 주요 뉴스 헤드라인 5~7개 수집

### 2단계: 거시경제 지표 수집
- WebSearch로 당일 USD/KRW 환율, WTI 유가, 브렌트 유가, 금 가격을 검색

### 3단계: Slack 발송
Slack MCP(`mcp__e9721764-2c13-4100-943a-65efb5f2b612__slack_send_message`)로 채널 `C0AR9KT6XDM`에 전송:

메시지 형식:
```
📊 주식시장 리포트 [날짜/시간]

🔑 핵심 요약
[오늘의 주요 포인트 3~4줄]

━━━ 🇰🇷 국내 ━━━
코스피 [지수] [등락률]
개인 [수급] | 외국인 [수급] | 기관 [수급]
코스닥 [지수] [등락률]
KOSPI200 [지수] [등락률]
종목현황: 상한[N] 상승[N] 보합[N] 하락[N]

📰 주요 뉴스
• [헤드라인 1]
• [헤드라인 2]
• [헤드라인 3]
• [헤드라인 4]
• [헤드라인 5]

━━━ 🇺🇸 미국 (전일종가) ━━━
S&P500 [지수] [등락률] | 나스닥 [지수] [등락률]
다우 [지수] [등락률] | 필반도체 [지수] [등락률]
DAX [지수] [등락률] | FTSE [지수] [등락률]

━━━ 🌐 거시지표 ━━━
USD/KRW [환율] | WTI $[유가] | 브렌트 $[유가] | 금 $[금값]/oz

━━━ 🔭 전망 & 투자 포인트 ━━━
[단기 핵심 변수 및 투자 포인트 3~4줄]

※ 본 리포트는 정보 제공 목적이며 투자 결정은 개인 판단하에 이루어져야 합니다.
```

## 주의사항
- finance.naver.com은 접근 차단됨 → 한국경제 데이터로 대체
- 현재 날짜/시간은 Bash로 확인: `date '+%Y년 %m월 %d일 %H시'`
