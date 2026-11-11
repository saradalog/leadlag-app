# リードラグ手帳

日米業種リードラグ戦略の毎朝の運用（今日の注文・窓チェック・口座の振り分け・成績・損益の入力・モデル比較）をスマホで行うWebアプリ（PWA）。GitHub Pages で https://saradalog.github.io/leadlag-app/ に配信し、ホーム画面に追加して使う。

- このリポジトリ（公開）には画面だけを置く。合言葉・Apps Script のURL・損益などの個人データはコードに入れない。
- データはスプレッドシート「米国シグナル」に付けた Apps Script（コードは非公開 `saradalog/leadlag-signal` の `webapp/Code_api.gs`、合言葉は伏せてある）から受け取る：`action=data`（GET）、`writeActual`（POST、本文JSON）。設定画面のURLと合言葉は localStorage の `ll-cfg`。
- 「今日の注文」は、本番（`leadlag-signal` の `leadlag_signal.py`）が毎朝書く「アプリ_今日の注文」シートを表示する。
- 画面を直したら `sw.js` の `CACHE`（`leadlag-shell-vN`）を+1する。
