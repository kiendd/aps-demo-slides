<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>APS Demo Bot · Kịch bản POC tính năng</title>
  <!--
    Bộ slide POC: mỗi slide một kịch bản tính năng, từ đơn giản đến phức tạp.
    Lời bot dựng theo mẫu câu trong src/ (mã nguồn bot), số liệu lấy từ dữ liệu demo ngày 28–30/10/2026.
    Phần do LLM viết được đánh dấu "(LLM)" trong ghi chú. Sửa nội dung ở mảng SCENARIOS phía dưới.
    Phím: ← → / Space chuyển slide, N ghi chú, F toàn màn hình, Home/End về đầu/cuối.
  -->
  <style>
    :root {
      --bg: #090d16;
      --surface: #111827;
      --surface-card: #162032;
      --surface-card-hover: #1c2940;
      --border: #23324d;
      --border-light: #334769;
      --text: #f3f4f6;
      --text-muted: #94a3b8;
      --text-dim: #64748b;
      --accent: #38bdf8;
      --primary: #2563eb;
      --success: #10b981;
      --warning: #f59e0b;
      --danger: #ef4444;
      --purple: #a855f7;
      --tg-bg: #0e1621;
      --tg-header: #17212b;
      --tg-in: #182533;
      --tg-out: #2b5278;
      --tg-btn: #22303f;
      --tg-link: #6ab3f3;
    }
    * { box-sizing: border-box; margin: 0; padding: 0; }
    body {
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
      background: var(--bg); color: var(--text);
      overflow: hidden; height: 100vh; width: 100vw;
    }
    #progress-bar {
      position: fixed; top: 0; left: 0; height: 4px; width: 0%; z-index: 100;
      background: linear-gradient(90deg, #2563eb, #38bdf8, #10b981);
      transition: width 0.3s ease;
    }
    .deck { position: relative; height: 100vh; width: 100vw; }
    .slide {
      position: absolute; inset: 0; margin: 0 auto; max-width: 1440px;
      padding: 36px 56px 72px; display: flex; flex-direction: column;
      opacity: 0; visibility: hidden; transform: translateY(16px);
      transition: opacity .35s ease, transform .35s ease, visibility .35s ease;
      overflow-y: auto;
    }
    .slide.active { opacity: 1; visibility: visible; transform: none; }

    /* Header */
    .badges { display: flex; gap: 8px; margin-bottom: 10px; flex-wrap: wrap; }
    .badge {
      display: inline-flex; align-items: center; gap: 6px; font-size: 12px; font-weight: 600;
      text-transform: uppercase; letter-spacing: 1px; padding: 4px 12px; border-radius: 999px;
      color: var(--accent); background: rgba(56,189,248,.1); border: 1px solid rgba(56,189,248,.25);
    }
    .badge.level { color: #c4b5fd; background: rgba(168,85,247,.1); border-color: rgba(168,85,247,.3); }
    .slide-title { font-size: 32px; font-weight: 700; color: #fff; letter-spacing: -.5px; line-height: 1.2; }
    .slide-subtitle { font-size: 16px; color: var(--text-muted); margin-top: 6px; line-height: 1.5; max-width: 1100px; }
    .slide-header { margin-bottom: 20px; }

    /* Scenario layout */
    .scenario { display: grid; grid-template-columns: minmax(380px, 470px) 1fr; gap: 32px; flex: 1; min-height: 0; }
    .side { display: flex; flex-direction: column; gap: 14px; min-width: 0; }
    .card {
      background: var(--surface-card); border: 1px solid var(--border); border-radius: 14px;
      padding: 16px 18px; display: flex; flex-direction: column; gap: 6px;
    }
    .card h4 { font-size: 15px; color: #fff; display: flex; gap: 8px; align-items: baseline; }
    .card h4 .n { color: var(--accent); font-weight: 800; }
    .card p { font-size: 14px; color: var(--text-muted); line-height: 1.55; }
    .side-label { font-size: 12px; font-weight: 700; text-transform: uppercase; letter-spacing: 1px; color: var(--text-dim); }
    .reqs { display: flex; flex-wrap: wrap; gap: 6px; }
    .req {
      font: 600 11px ui-monospace, SFMono-Regular, Menlo, monospace; color: #93c5fd;
      background: rgba(37,99,235,.12); border: 1px solid rgba(37,99,235,.35); padding: 3px 8px; border-radius: 6px;
    }
    .footnote { font-size: 12px; color: var(--text-dim); line-height: 1.5; margin-top: auto; }

    /* Telegram mock */
    .phone {
      background: var(--tg-bg); border: 1px solid #1f2c3b; border-radius: 22px; overflow: hidden;
      display: flex; flex-direction: column; min-height: 0; max-height: calc(100vh - 226px);
      box-shadow: 0 18px 40px rgba(0,0,0,.45);
    }
    .phone-head {
      background: var(--tg-header); padding: 10px 16px; display: flex; align-items: center; gap: 10px;
      border-bottom: 1px solid #0b121a; flex-shrink: 0;
    }
    .avatar {
      width: 34px; height: 34px; border-radius: 50%; display: grid; place-items: center; font-weight: 800; font-size: 14px;
      background: linear-gradient(135deg, #2563eb, #10b981); color: #fff;
    }
    .phone-head .name { font-size: 14px; font-weight: 600; color: #fff; }
    .phone-head .status { font-size: 12px; color: var(--tg-link); }
    .chat { padding: 12px 12px 16px; display: flex; flex-direction: column; gap: .6em; overflow-y: auto; font-size: 13px; }
    .msg { max-width: 88%; line-height: 1.45; white-space: pre-wrap; word-break: break-word; }
    .msg .bubble { padding: 8px 11px; border-radius: 12px; }
    .msg.user { align-self: flex-end; }
    .msg.user .bubble { background: var(--tg-out); color: #fff; border-bottom-right-radius: 4px; }
    .msg.bot { align-self: flex-start; }
    .msg.bot .bubble { background: var(--tg-in); color: #e8eef5; border-bottom-left-radius: 4px; }
    .msg .link { color: var(--tg-link); word-break: break-all; }
    .msg .llm { border-left: 2px solid var(--purple); padding-left: 7px; display: block; }
    .kb { display: flex; flex-direction: column; gap: 3px; margin-top: 3px; }
    .kb-row { display: flex; gap: 3px; }
    .kb-btn {
      flex: 1; text-align: center; font-size: .92em; color: #fff; background: var(--tg-btn);
      padding: .4em .6em; border-radius: 6px; white-space: nowrap; overflow: hidden; text-overflow: ellipsis;
    }
    .kb-btn.hit { outline: 1.5px solid var(--accent); background: #24415e; }
    .tap, .sys {
      align-self: center; font-size: .885em; padding: 3px 10px; border-radius: 999px; text-align: center; max-width: 92%;
    }
    .tap { color: var(--accent); background: rgba(56,189,248,.1); }
    .sys { color: #cbd5e1; background: rgba(255,255,255,.07); }
    .legend { margin-left: auto; font-size: 11.5px; color: var(--text-dim); display: flex; align-items: center; }
    .legend i { display: inline-block; width: 8px; height: 12px; border-left: 2px solid var(--purple); margin-right: 4px; }

    /* Overview */
    .levels { display: grid; grid-template-columns: repeat(3, 1fr); gap: 16px; }
    .level-card { background: var(--surface-card); border: 1px solid var(--border); border-radius: 14px; padding: 16px 18px; }
    .level-card h3 { font-size: 15px; color: #c4b5fd; margin-bottom: 4px; }
    .level-card .why { font-size: 13px; color: var(--text-muted); margin-bottom: 10px; line-height: 1.5; }
    .level-card ol { list-style: none; display: flex; flex-direction: column; gap: 6px; }
    .level-card li { font-size: 14px; display: flex; gap: 10px; cursor: pointer; }
    .level-card li:hover { color: var(--accent); }
    .level-card li .num { color: var(--accent); font-weight: 700; font-variant-numeric: tabular-nums; min-width: 22px; }

    /* Title */
    .title-slide { justify-content: center; gap: 22px; }
    .title-slide h1 { font-size: 52px; letter-spacing: -1px; line-height: 1.1; }
    .title-slide h1 span { background: linear-gradient(90deg, #38bdf8, #10b981); -webkit-background-clip: text; background-clip: text; color: transparent; }
    .title-slide .lead { font-size: 20px; color: var(--text-muted); max-width: 900px; line-height: 1.5; }
    .stats { display: grid; grid-template-columns: repeat(3, 1fr); gap: 14px; margin-top: 10px; width: 100%; }
    .stat { background: var(--surface-card); border: 1px solid var(--border); border-radius: 14px; padding: 18px 22px; display: flex; flex-direction: column; gap: 4px; }
    .stat b { display: block; font-size: 32px; font-weight: 800; color: #fff; line-height: 1.1; }
    .stat span { font-size: 13.5px; color: var(--text-muted); line-height: 1.45; }

    /* Flow & screens */
    .flow { display: flex; flex-direction: column; gap: 8px; }
    .flow-step { display: grid; grid-template-columns: 34px 1fr; gap: 12px; align-items: start; }
    .flow-step .dot {
      width: 34px; height: 34px; border-radius: 50%; display: grid; place-items: center; font-weight: 800; font-size: 14px;
      background: rgba(56,189,248,.12); color: var(--accent); border: 1px solid rgba(56,189,248,.35);
    }
    .flow-step .body { background: var(--surface-card); border: 1px solid var(--border); border-radius: 12px; padding: 10px 14px; }
    .flow-step .body b { font-size: 14px; color: #fff; }
    .flow-step .body p { font-size: 13px; color: var(--text-muted); line-height: 1.5; margin-top: 2px; }
    .screens { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; }
    .screen { background: var(--surface-card); border: 1px solid var(--border); border-radius: 12px; padding: 12px 14px; }
    .screen code { font: 600 12px ui-monospace, Menlo, monospace; color: var(--success); }
    .screen b { display: block; font-size: 14px; color: #fff; margin: 3px 0; }
    .screen p { font-size: 13px; color: var(--text-muted); line-height: 1.5; }

    .principles { display: grid; grid-template-columns: repeat(3, 1fr); gap: 16px; }
    .principle { border-radius: 14px; padding: 18px; border: 1px solid; }
    .principle h3 { font-size: 17px; margin-bottom: 6px; }
    .principle p { font-size: 14px; color: var(--text-muted); line-height: 1.55; }
    .p-green { background: rgba(16,185,129,.06); border-color: rgba(16,185,129,.3); } .p-green h3 { color: #34d399; }
    .p-yellow { background: rgba(245,158,11,.06); border-color: rgba(245,158,11,.3); } .p-yellow h3 { color: #fbbf24; }
    .p-red { background: rgba(239,68,68,.06); border-color: rgba(239,68,68,.3); } .p-red h3 { color: #f87171; }

    /* Controls */
    .controls {
      position: fixed; bottom: 0; left: 0; right: 0; height: 52px; z-index: 100;
      background: rgba(11,15,25,.9); backdrop-filter: blur(10px); border-top: 1px solid var(--border);
      display: flex; align-items: center; justify-content: space-between; padding: 0 28px;
    }
    .controls > div { display: flex; align-items: center; gap: 12px; }
    .btn {
      background: var(--surface-card); border: 1px solid var(--border); color: var(--text);
      padding: 6px 14px; border-radius: 8px; font-size: 13px; cursor: pointer;
    }
    .btn:hover { background: var(--surface-card-hover); border-color: var(--border-light); }
    .counter { font-size: 13px; font-weight: 600; color: var(--text-muted); }
    #notes-panel {
      position: fixed; bottom: 52px; right: 28px; width: 480px; max-height: 300px; z-index: 99;
      background: #0f172a; border: 1px solid var(--border-light); border-radius: 12px; padding: 16px 20px;
      box-shadow: 0 10px 25px rgba(0,0,0,.5); display: none; flex-direction: column; gap: 8px; overflow-y: auto;
    }
    #notes-panel.open { display: flex; }
    #notes-panel h4 { font-size: 12px; color: var(--accent); text-transform: uppercase; letter-spacing: .5px; }
    #notes-content { font-size: 13.5px; color: var(--text-muted); line-height: 1.55; }

    /* Mobile Responsive (<= 900px) */
    @media (max-width: 900px) {
      .slide {
        padding: 16px 14px 68px;
        overflow-y: auto;
        -webkit-overflow-scrolling: touch;
      }
      .slide-title { font-size: 22px; line-height: 1.25; }
      .slide-subtitle { font-size: 13.5px; line-height: 1.45; }
      .slide-header { margin-bottom: 14px; }
      
      /* Title Slide */
      .title-slide { justify-content: flex-start; padding-top: 24px; gap: 14px; }
      .title-slide h1 { font-size: 30px; }
      .title-slide .lead { font-size: 14px; line-height: 1.45; }
      .stats { grid-template-columns: 1fr; gap: 10px; margin-top: 6px; }
      .stat { padding: 12px 14px; }
      .stat b { font-size: 24px; }
      .stat span { font-size: 12px; }

      /* Menu / Overview Slide */
      .levels { grid-template-columns: 1fr; gap: 12px; }
      .level-card { padding: 12px 14px; }
      .level-card h3 { font-size: 14px; }
      .level-card .why { font-size: 12px; margin-bottom: 8px; }
      .level-card li { font-size: 13px; }

      /* Scenarios */
      .scenario {
        display: flex;
        flex-direction: column;
        gap: 16px;
      }
      .phone {
        max-height: none;
        border-radius: 16px;
        box-shadow: 0 8px 24px rgba(0,0,0,.35);
      }
      .phone-head { padding: 8px 12px; }
      .avatar { width: 28px; height: 28px; font-size: 12px; }
      .phone-head .name { font-size: 13px; }
      .phone-head .status { font-size: 11px; }
      .chat { padding: 10px 10px 14px; font-size: 12px; }
      .msg .bubble { padding: 7px 10px; border-radius: 10px; }
      .legend { display: none; }

      /* Screens (Trang quản trị web) */
      .screens { grid-template-columns: 1fr; gap: 8px; }
      .screen { padding: 10px 12px; }
      .screen b { font-size: 13px; }
      .screen p { font-size: 12px; }

      /* Summary Slide */
      .principles { grid-template-columns: 1fr; gap: 10px; }
      .principle { padding: 14px; }
      .principle h3 { font-size: 15px; }
      .principle p { font-size: 13px; }

      /* Controls bar on Mobile */
      .controls {
        height: 48px;
        padding: 0 10px;
      }
      .controls > div { gap: 6px; }
      .btn {
        padding: 5px 8px;
        font-size: 11.5px;
        border-radius: 6px;
      }
      .counter { font-size: 11px; }
      #btn-notes { display: none; }
      #btn-fs { display: none; }
      #notes-panel {
        left: 10px; right: 10px; width: auto; bottom: 50px;
      }
    }
    @media print {
      @page { size: 1440px 900px; margin: 0; }
      body { overflow: visible; height: auto; }
      .controls, #progress-bar, #notes-panel { display: none !important; }
      .deck { height: auto; }
      .slide {
        position: relative !important; opacity: 1 !important; visibility: visible !important; transform: none !important;
        height: 900px; width: 1440px; page-break-after: always; overflow: hidden; background: var(--bg);
        -webkit-print-color-adjust: exact; print-color-adjust: exact;
      }
      .phone { max-height: 680px; }
    }
  </style>
</head>
<body>
  <div id="progress-bar"></div>
  <div class="deck" id="deck"></div>

  <div class="controls">
    <div>
      <button class="btn" onclick="go(current - 1)" title="Mũi tên trái">◀ Trước</button>
      <button class="btn" onclick="go(current + 1)" title="Mũi tên phải / Space">Tiếp ▶</button>
      <span class="counter" id="counter"></span>
    </div>
    <div>
      <button class="btn" onclick="go(1)" title="Về slide menu">☰ Menu</button>
      <button class="btn" id="btn-notes" onclick="toggleNotes()" title="Phím N">📝 Ghi chú</button>
      <button class="btn" id="btn-fs" onclick="toggleFullScreen()" title="Phím F">⛶ Toàn màn hình</button>
    </div>
  </div>
  <div id="notes-panel"><h4>Gợi ý thuyết trình</h4><div id="notes-content"></div></div>

  <script>
    /*
     * Cú pháp hội thoại:
     *   { u: "..." }                       người dùng gõ
     *   { b: "...", kb: [["A","B"],["C"]] } bot trả lời; kb là các hàng nút inline; tiền tố "*" = nút được bấm tiếp theo
     *   { b: "...", llm: "..." }           phần llm (do LLM viết, đã qua bộ chặn) chèn ở vị trí {LLM} trong b
     *   { tap: "..." }                     người dùng bấm nút
     *   { sys: "..." }                     mốc thời gian / sự kiện hệ thống
     * Mẫu câu theo src/; số liệu từ dữ liệu demo 28–30/10/2026 (giá: APEC, chỉ số và cổ đông lớn: VNDirect).
     */
    const RATE = ["👍", "👎"];
    const LEVELS = [
      { key: "1", name: "Cấp 1 · Tra cứu một chạm", why: "Một câu hỏi, một câu trả lời có nguồn." },
      { key: "2", name: "Cấp 2 · Tra cứu theo hồ sơ", why: "Trả lời từ tài liệu APS và danh mục của chính người hỏi." },
      { key: "3", name: "Cấp 3 · Hiểu hội thoại", why: "Nhận ra nhân vật, nhớ chủ thể giữa các câu hỏi." },
      { key: "4", name: "Cấp 4 · Giải thích có kiểm soát", why: "LLM viết lời, code kiểm từng con số và từng cụm từ." },
      { key: "5", name: "Cấp 5 · Bot chủ động", why: "Bot tự theo dõi giá và tin, tự gửi khi đến ngưỡng." },
      { key: "6", name: "Cấp 6 · Vận hành & quản trị", why: "Dữ liệu được thu, bóc tách, hậu kiểm và giám sát." },
    ];

    const SCENARIOS = [
      {
        level: "1", title: "Xã giao & câu hỏi mẫu",
        tagline: "Người dùng mới không cần biết hỏi gì: bot giới thiệu đúng những việc nó làm được và đưa sẵn bốn câu hỏi mẫu.",
        chat: [
          { u: "Chào bạn, bạn làm được gì?" },
          { b: "{LLM}", llm: "Chào bạn! Mình có thể giúp: xem giá một mã, tin hôm nay, hỏi đáp tài liệu APS, so sánh hai mã, xem tỷ trọng ngành trong danh mục mô phỏng và đặt cảnh báo giá (mình không đưa lời khuyên mua bán). Bạn thử một câu bên dưới hoặc dùng Menu chính nhé.",
            kb: [RATE, ["*Giá HPG", "Tin về FPT"], ["Phí giao dịch APS", "So sánh HPG và FPT"]] },
          { tap: "Giá HPG" },
          { b: "📊 HPG · 21.000 đ\n\n• Khối ngoại hôm nay: mua 5.823.300 cp (123,9 tỷ đ), bán 6.033.200 cp (127,9 tỷ đ).\n• Room khối ngoại còn lại: 2.296.677.910 cp.\n\nNguồn: APEC, giá lúc 15:00 30/10/2026", kb: [RATE] },
        ],
        points: [
          ["Chỉ giới thiệu việc có thật", "Danh sách năng lực cố định trong code; LLM chỉ viết lại cho tự nhiên, không được hứa thêm."],
          ["Lời LLM vẫn qua kiểm", "Quá dài, có cụm từ cấm hoặc có số lạ thì bot dùng câu dựng sẵn thay thế."],
          ["Không có ngõ cụt", "Câu xã giao và câu chưa hỗ trợ luôn kèm bốn nút câu hỏi mẫu; câu chưa hỗ trợ thêm nút Gặp môi giới."],
        ],
        reqs: ["REQ-HOI-DAP-021", "REQ-HOI-DAP-025", "REQ-HOI-DAP-026"],
        notes: "Mở màn nhẹ: gõ lời chào, bấm nút 'Giá HPG'. Nhấn mạnh bot xưng 'mình', gọi 'bạn', trả lời gọn trong một màn hình. Lời chào do LLM viết (viền tím) nhưng đã qua bộ chặn.",
      },
      {
        level: "1", title: "Hỏi giá một mã",
        tagline: "Giá kèm khối ngoại, nguồn và giờ của giá; tên gõ khớp nhiều mã thì bot hỏi lại thay vì đoán.",
        chat: [
          { u: "Giá HPG bây giờ bao nhiêu?" },
          { b: "📊 HPG · 21.000 đ\n\n• Khối ngoại hôm nay: mua 5.823.300 cp (123,9 tỷ đ), bán 6.033.200 cp (127,9 tỷ đ).\n• Room khối ngoại còn lại: 2.296.677.910 cp.\n\nNguồn: APEC, giá lúc 15:00 30/10/2026", kb: [RATE] },
          { u: "giá Hòa Bình" },
          { b: "Tên \"Hòa Bình\" khớp nhiều mã: HBC (Xây dựng Hòa Bình), HBS (CK Hòa Bình), HRC (Cao su Hòa Bình). Bạn muốn hỏi mã nào?", kb: [RATE] },
        ],
        points: [
          ["Nguồn thật, giờ thật", "Dòng Nguồn nêu đúng nguồn đã trả con số (APEC, dự phòng VNDirect); nhiều mã thì nêu giờ của giá cũ nhất."],
          ["Gõ tên tự do", "Khớp không phân biệt dấu, hoa thường: \"thép Hòa Phát\" ra HPG; khớp nhiều mã thì liệt kê và hỏi lại."],
          ["Nguồn lỗi thì nói lỗi", "Nguồn giá không truy cập được thì bot báo chưa báo giá được, không đưa con số nào. Mã APF có ghi chú không phải bộ phận APF của APEC."],
        ],
        reqs: ["REQ-HOI-DAP-012", "REQ-DU-LIEU-THI-TRUONG-004", "REQ-DU-LIEU-THI-TRUONG-012", "REQ-DU-LIEU-THI-TRUONG-013"],
        notes: "Danh sách 3 mã 'Hòa Bình' là kết quả thật của bộ phân giải tên trên danh sách 1.518 mã niêm yết. Có thể demo thêm 'giá APF' để thấy dòng ghi chú trùng tên.",
      },
      {
        level: "1", title: "Chỉ số tài chính",
        tagline: "Năm chỉ số P/E, P/B, EPS, BVPS, ROE đúng số của nguồn, ghi rõ ngày báo cáo của từng chỉ tiêu.",
        chat: [
          { u: "P/E của FPT?" },
          { b: "📊 Chỉ số tài chính của FPT (CTCP FPT):\n\n• P/E: 9.66\n• P/B: 2.32\n• EPS 4 quý (đ): 5.456 (ngày 30/09/2026)\n• BVPS (đ): 22.736\n• ROE: 24,4% (ngày 30/09/2026)\n\nNguồn: VNDirect, số liệu tới ngày 30/10/2026", kb: [RATE] },
        ],
        points: [
          ["Nhận diện bằng luật", "Câu hỏi về năm chỉ số được bắt bằng luật trên câu chữ, chạy trước bộ phân loại LLM: nhanh và không phân loại nhầm."],
          ["Ngày nào ra ngày đó", "P/E, P/B, BVPS cập nhật theo phiên; EPS, ROE theo quý. Chỉ tiêu nào khác ngày mới nhất thì ghi ngày riêng."],
          ["Không tự tính, không phán", "Bot không suy thêm chỉ số ngoài năm chỉ số của nguồn và không kết luận mã đắt hay rẻ."],
        ],
        reqs: ["REQ-HOI-DAP-001", "REQ-HOI-DAP-014", "REQ-DU-LIEU-THI-TRUONG-014", "REQ-DU-LIEU-THI-TRUONG-015"],
        notes: "Số liệu lấy trực tiếp từ API VNDirect ngày 30/10/2026. Nếu bị hỏi 'vậy FPT rẻ không', chuyển sang kịch bản Đèn giao thông.",
      },
      {
        level: "1", title: "Tin hôm nay",
        tagline: "Tin trong ngày về một mã, mỗi tin một dòng tóm tắt tiếng Việt kèm tên báo, giờ đăng và link gốc.",
        chat: [
          { sys: "Tối 28/10/2026" },
          { u: "Hôm nay có tin gì về FPT?" },
          { b: "📰 Tin hôm nay về FPT (2 tin):\n\n• {LLM}\n  (CafeF, 22:49 28/10/2026)\n  https://cafef.vn/co-phieu-thung-day-3-nam-fpt-phat-thong-bao-quan-trong-188261028224606129.chn\n• Khối ngoại bán ròng trong phiên 28/10, kéo dài chuỗi bán ròng lên 4 phiên liên tiếp; lực bán tập trung cao vào cổ phiếu FPT.\n  (Vietstock, 19:26 28/10/2026)\n  http://vietstock.vn/2026/10/theo-dau-dong-tien-ca-map-2810-khoi-ngoai-ban-rong-manh-fpt-830-1508126.htm\n\nNguồn: CafeF, Vietstock, tin mới nhất lúc 22:49 28/10/2026",
            llm: "FPT phát thông báo về việc thanh toán cổ tức với ngày đăng ký cuối cùng là 30/11/2026 và thời gian thanh toán dự kiến 10/12/2026.", kb: [RATE] },
        ],
        points: [
          ["Tóm tắt có kiểm", "Tóm tắt do LLM viết lúc thu tin; tóm tắt nào chứa cụm từ cấm thì bot dùng tiêu đề gốc của báo."],
          ["Tin thị trường hôm nay", "Hỏi \"thị trường có tin gì\" không nêu mã: tối đa 8 Sự kiện toàn thị trường, mức Cao trước rồi Trung bình."],
          ["Nguồn lỗi được nêu tên", "Chưa có tin thì nói chưa có; nguồn tin đang đọc lỗi thì nêu tên nguồn đó."],
        ],
        reqs: ["REQ-HOI-DAP-013", "REQ-HOI-DAP-028"],
        notes: "Hai tin là tin thật đã lưu ngày 28/10/2026. Demo thêm 'Hôm nay thị trường có tin gì?' để thấy Tin thị trường hôm nay.",
      },
      {
        level: "2", title: "Hỏi đáp Kho tài liệu APS",
        tagline: "Phí, thủ tục, quy định: bot trả lời chỉ từ các trang apec.com.vn và văn bản pháp lý đã thu, kèm link từng tài liệu.",
        chat: [
          { u: "Phí giao dịch tại APS là bao nhiêu?" },
          { b: "📄 Từ tài liệu của APS\n\n{LLM}\n\nNguồn: Mức phí giao dịch tại APS đang áp dụng như thế nào? · thu thập ngày 28/10/2026 · https://apec.com.vn/ho-tro/10-muc-phi-giao-dich-tai-aps-dang-ap-dung-nhu-the-nao/\nNguồn: Ngoài phí quản lý tài khoản, khách hàng còn phải nộp phí nào khác không? · thu thập ngày 28/10/2026 · https://apec.com.vn/ho-tro/11-ngoai-phi-quan-ly-tai-khoan-khach-hang-con-phai-nop-phi-nao-khac-khong/",
            llm: "Phí giao dịch tại APS tuỳ loại hình tài khoản: loại hình Smart, Loyal là 0.1% tổng giá trị giao dịch; loại hình A Broker Plus là 0.2%. Khi đăng ký gói dịch vụ Basic, Standard, Premium hoặc VIP, bạn được miễn phí giao dịch tại APS, nhưng vẫn nộp phí cho UBCK và Sở giao dịch 0.03% trên tổng giá trị giao dịch khớp lệnh.", kb: [RATE] },
          { u: "Mở tài khoản phái sinh tại văn phòng Cần Thơ thế nào?" },
          { b: "Mình không tìm thấy nội dung này trong tài liệu về APS mà mình có. Bạn bấm \"Gặp môi giới\" để nhờ người của APEC hỗ trợ.", kb: [RATE, ["Gặp môi giới"]] },
        ],
        points: [
          ["Chỉ nói điều tài liệu nói", "Bot tìm đoạn gần nhất theo độ tương đồng; không đoạn nào đạt ngưỡng thì trả lời không tìm thấy."],
          ["Chặn số lạ", "Số nào trong câu trả lời không có trong đoạn tài liệu thì bot gọi LLM viết lại một lần; vẫn sai thì trích nguyên đoạn."],
          ["Trích dẫn kiểm được", "Tối đa 3 tài liệu, mỗi tài liệu một dòng: tên, ngày thu thập, link gốc; văn bản pháp lý kèm Điều, khoản."],
        ],
        reqs: ["REQ-HOI-DAP-015", "REQ-KHO-TAI-LIEU-009", "REQ-KHO-TAI-LIEU-010", "REQ-KHO-TAI-LIEU-011", "REQ-KHO-TAI-LIEU-012", "REQ-KHO-TAI-LIEU-013"],
        notes: "Các con số 0.1%, 0.2%, 0.03% có trong hai trang FAQ thật của apec.com.vn mà bot thu ngày 28/10/2026. Kho tài liệu tự làm mới mỗi 7 ngày.",
      },
      {
        level: "2", title: "Danh mục mô phỏng",
        tagline: "Người dùng thử chọn một Mẫu khách và có ngay danh mục để hỏi: giá vốn, giá hiện tại, tỷ trọng theo mã và theo ngành.",
        chat: [
          { sys: "Người dùng đã chọn Mẫu khách Cân bằng (Thận trọng · Cân bằng · Tích cực)" },
          { u: "Danh mục của tôi" },
          { b: "📊 Danh mục của bạn (dữ liệu mô phỏng, mẫu Cân bằng):\n\n• HPG: 1.000 cp, giá vốn 19.800 đ, giá hiện tại 21.000 đ\n• FPT: 200 cp, giá vốn 52.000 đ, giá hiện tại 52.700 đ\n• VCB: 150 cp, giá vốn 90.000 đ, giá hiện tại 56.300 đ\n• MWG: 200 cp, giá vốn 60.000 đ, giá hiện tại 74.000 đ\n• SSI: 500 cp, giá vốn 28.000 đ, giá hiện tại 19.300 đ\n\nNguồn: APEC, giá lúc 15:00 30/10/2026", kb: [RATE] },
          { u: "Danh mục của tôi có tập trung quá không?" },
          { b: "📊 Tỷ trọng theo giá trị thị trường hiện tại của danh mục mô phỏng.\n\n{LLM}\n\nNguồn: APEC, giá lúc 15:00 30/10/2026\nDữ liệu mô phỏng.\nĐây là thông tin tham khảo, không phải khuyến nghị đầu tư.",
            llm: "Danh mục mô phỏng có 5 mã thuộc 5 ngành. Theo giá trị thị trường hiện tại, HPG (Tài nguyên) chiếm 32,6%, MWG (Dịch vụ bán lẻ) 23,0%, FPT (Công nghệ) 16,4%, SSI (Dịch vụ tài chính) 15,0% và VCB (Ngân hàng) 13,1%. Chưa có ngưỡng tập trung nào để đối chiếu, nên mình chỉ nêu tỷ trọng.", kb: [RATE] },
        ],
        points: [
          ["Luôn nói rõ là mô phỏng", "Ba Mẫu khách với mã thật, số lượng và giá vốn giả; mọi câu trả lời ghi \"dữ liệu mô phỏng\"."],
          ["Code tính, LLM diễn đạt", "Tỷ trọng theo mã và theo ngành do code tính; không có ngưỡng thì bot nói chưa có ngưỡng, không tự đặt."],
          ["Nối sang tin tức", "Chọn Mẫu khách là tự Đăng ký quan tâm các công ty trong danh mục, và hỏi được \"tin mới về danh mục của tôi\"."],
        ],
        reqs: ["REQ-HOI-DAP-016", "REQ-HOI-DAP-020", "REQ-HOI-DAP-029", "REQ-TIN-TUC-023"],
        notes: "Giá hiện tại là giá thật cuối phiên 30/10/2026; giá vốn là số giả của Mẫu khách Cân bằng. Không cần liên kết tài khoản thật trong giai đoạn thử.",
      },
      {
        level: "2", title: "So sánh hai mã",
        tagline: "Đặt hai mã cạnh nhau bằng giá và chỉ số của nguồn; lời so sánh do LLM viết nhưng không được thêm số nào.",
        chat: [
          { u: "So sánh FPT với VNM" },
          { b: "⚖️ So sánh FPT và VNM\n\n{LLM}\n\nNguồn: APEC, giá lúc 15:00 30/10/2026\nĐây là thông tin tham khảo, không phải khuyến nghị đầu tư.",
            llm: "FPT (CTCP FPT, ngành Công nghệ) đang ở mức giá 52.700 đ, còn VNM (VINAMILK, ngành Thực phẩm & Đồ uống) ở mức 56.900 đ; cả hai niêm yết trên sàn HOSE. Hai mã thuộc hai ngành khác nhau nên chỉ số tài chính phản ánh hai mô hình kinh doanh khác nhau.", kb: [RATE] },
          { u: "Vậy nên mua FPT hay VNM?" },
          { b: "🛡️ Mình không đưa ra ý kiến mua bán, rủi ro hay pháp lý. Đó là quyết định của riêng bạn và cần người có chuyên môn của APEC.\n\nNếu cần ý kiến chuyên môn, bấm \"Gặp môi giới\" để nhờ người của APEC hỗ trợ.\nĐây là thông tin tham khảo, không phải khuyến nghị đầu tư.", kb: [RATE, ["Gặp môi giới"]] },
        ],
        points: [
          ["Dữ kiện do code dựng", "Sàn, ngành, giá và năm chỉ số của mỗi mã được đưa vào làm dữ kiện; LLM chỉ so sánh bằng lời."],
          ["Thiếu giá thì dừng", "Thiếu giá của một trong hai mã thì bot nói thiếu mã nào, không so sánh nửa vời."],
          ["Ranh giới với tư vấn", "Câu tiếp theo xin chọn mua mã nào lập tức sang nhánh đỏ: từ chối và đưa nút Gặp môi giới."],
        ],
        reqs: ["REQ-HOI-DAP-020", "REQ-HOI-DAP-002", "REQ-HOI-DAP-006"],
        notes: "Câu 'so sánh FPT với VNM' là câu Người dùng thử đã hỏi thật. Lời so sánh là ví dụ cách LLM viết; số nào không có trong dữ kiện sẽ bị chặn.",
      },
      {
        level: "3", title: "Nhân vật & cổ đông lớn",
        tagline: "Hỏi \"X là ai\" bằng tên hoặc biệt danh: bot trả lời từ hồ sơ bóc từ tin và số cổ phiếu trong danh sách cổ đông lớn.",
        chat: [
          { u: "Cường Đô La là ai?" },
          { b: "👤 Nguyễn Quốc Cường (Quốc Cường Gia Lai, Tổng Giám đốc)\n\n• Cường Đô-la dùng siêu xe Lamborghini Temerario giá 30 tỷ đồng làm giải thưởng bốc thăm cho khách mua nhà tại dự án Solina Luxury Apartments.\n  (CafeF, 20:15 30/10/2026)\n  https://cafef.vn/muon-duoc-cuong-do-la-tang-sieu-xe-lamborghini-temerario-gia-30-ty-dong-ban-se-can-co-du-3-dieu-kien-188261030201554535.chn\n• Bà Nguyễn Thị Như Loan trở lại giữ chức Tổng Giám đốc Quốc Cường Gia Lai (QCG), thay thế ông Nguyễn Quốc Cường.\n  (CafeF, 10:01 14/10/2026)\n  https://cafef.vn/cuong-do-la-chia-tay-co-phieu-qcg-co-bien-188261014094124213.chn\n\nNguồn: CafeF, tin mới nhất lúc 20:15 30/10/2026", kb: [RATE] },
          { u: "đang nắm bao nhiêu cổ phiếu?" },
          { b: "👤 Nguyễn Quốc Cường\n\n• Đang nắm 537.500 cổ phiếu (0,2% vốn) của mã QCG, hiệu lực từ 30/06/2020.\n\nNguồn: VNDirect.", kb: [RATE] },
        ],
        points: [
          ["Biệt danh vẫn nhận ra", "Đối tượng tin lưu mọi tên gọi khác đã gặp trong báo (Cường Đô La, CDL, NQC); hồ sơ dựng từ dữ liệu đã lưu, không gọi LLM."],
          ["Số cổ phiếu neo theo công ty", "Chỉ trả lời khi danh sách cổ đông lớn có đúng một dòng khớp cả tên người lẫn mã công ty của người đó."],
          ["Không có thì nói không có", "Người lạ hoặc không khớp dòng nào: \"Mình chưa có dữ liệu…\", không đưa con số."],
        ],
        reqs: ["REQ-HOI-DAP-031", "REQ-HOI-DAP-032", "REQ-HOI-DAP-034", "REQ-DU-LIEU-THI-TRUONG-023"],
        notes: "Đây là câu Người dùng thử hỏi nhiều nhất trong Nhật ký. Câu thứ hai không có chủ ngữ: bot nhớ chủ thể vừa nói (xem kịch bản tiếp theo). Danh sách cổ đông lớn đồng bộ từ VNDirect mỗi 24 giờ; bản sửa tỷ lệ phần trăm (fix-ty-le-so-huu-co-phan) có hiệu lực sau lượt đồng bộ đầu tiên khi bot khởi động lại.",
      },
      {
        level: "3", title: "Nhớ chủ thể",
        tagline: "Đọc xong Bản tin, người dùng hỏi tiếp không cần gõ lại mã: bot hiểu theo tin vừa gửi, và hỏi lại bằng nút khi tin có nhiều mã.",
        chat: [
          { sys: "15:00 30/10/2026 — bot gửi Bản tin cuối phiên" },
          { b: "📰 Bản tin cuối phiên 30/10/2026: 2 tin về đối tượng bạn quan tâm.\n\n⚡ FPT — Khối ngoại bán ròng phiên 28/10, kéo dài chuỗi bán ròng lên 4 phiên liên tiếp; lực bán tập trung vào FPT · Giá: 52.700 đ\n   http://vietstock.vn/2026/10/theo-dau-dong-tien-ca-map-2810-khoi-ngoai-ban-rong-manh-fpt-830-1508126.htm\n\n⚡ HPG — Người thân lãnh đạo Hòa Phát bán thành công cổ phiếu như đăng ký · Giá: 21.000 đ\n   https://cafef.vn/nguoi-than-lanh-dao-hoa-phat-ban-thanh-cong-co-phieu-nhu-dang-ky-188261015141024258.chn" },
          { u: "giá thế nào?" },
          { b: "Bạn muốn hỏi về mã nào?", kb: [["*FPT", "HPG"]] },
          { tap: "FPT" },
          { b: "📊 FPT · 52.700 đ\n\n• Khối ngoại hôm nay: mua 515.800 cp (27,3 tỷ đ), bán 518.400 cp (27,5 tỷ đ).\n• Room khối ngoại còn lại: 379.197.860 cp.\n\nNguồn: APEC, giá lúc 15:00 30/10/2026", kb: [RATE] },
        ],
        points: [
          ["Nhớ từ hai phía", "Chủ thể lấy từ câu trả lời gần nhất, hoặc từ Bản tin, Cảnh báo giá, Cảnh báo biến động giá mà bot vừa tự gửi."],
          ["Không đoán khi mơ hồ", "Tin có từ hai đối tượng trở lên thì bot hỏi lại kèm nút; bấm nút trả lời ngay, không trừ lượt tin nhắn."],
          ["Biết lúc nào không áp dụng", "Lời chào, câu khái niệm, câu tin toàn thị trường và câu nói về chính người dùng được xử lý như câu độc lập."],
        ],
        reqs: ["REQ-HOI-DAP-033", "REQ-HOI-DAP-037", "REQ-HOI-DAP-038"],
        notes: "Đây là trải nghiệm 'như nhắn với môi giới': đọc bản tin trên điện thoại rồi hỏi cụt 'giá thế nào?'. Sau khi bấm FPT, câu tiếp theo tự hiểu là FPT.",
      },
      {
        level: "4", title: "Giải thích biến động giá",
        tagline: "\"Vì sao FPT giảm?\": dữ kiện giá do code tính, lý do chỉ lấy từ tin về mã đó trong 7 ngày, luôn có câu miễn trừ và nút Gặp môi giới.",
        chat: [
          { sys: "15:00 29/10/2026" },
          { u: "Vì sao FPT giảm?" },
          { b: "📉 Vì sao FPT giảm\n\n• Hôm nay FPT giảm 2,4% so với phiên 28/10 (54.000 đ → 52.700 đ).\n• So với 5 phiên trước (22/10, 57.400 đ): giảm 8,2%.\n• So với 20 phiên trước (01/10, 62.700 đ): giảm 15,9%.\n• Đỉnh đóng cửa trong 20 phiên gần nhất: 62.100 đ ngày 02/10; giá hiện tại thấp hơn đỉnh 15,1%.\n\n{LLM}\n\nNguồn: APEC, giá lúc 15:00 29/10/2026\nNguồn: Vietstock, CafeF, tin mới nhất lúc 22:49 28/10/2026\nĐây là phân tích từ tin tức, không phải khuyến nghị đầu tư.",
            llm: "Theo Vietstock ngày 28/10, khối ngoại bán ròng phiên 28/10, kéo dài chuỗi bán ròng lên 4 phiên liên tiếp với lực bán tập trung vào FPT. Trước đó, CafeF ngày 26/10 cho biết khối ngoại bán ròng gần 900 tỷ đồng trên HoSE, trong đó FPT chịu áp lực lớn nhất.",
            kb: [RATE, ["Gặp môi giới"]] },
        ],
        points: [
          ["Số do code, lời do LLM", "Biến động 1, 5, 20 phiên, đỉnh 20 phiên, khối ngoại, cùng ngành: code tính từ Giá theo ngày. Số nào LLM thêm mà không có trong dữ kiện bị chặn."],
          ["Lý do phải có nguồn", "Lý do chỉ lấy từ tin về chính mã đó trong 7 ngày; Bối cảnh thị trường chỉ là bối cảnh, bị bỏ nếu nói nhân quả."],
          ["Phân tích cổ phiếu", "\"Phân tích FPT\" dùng cùng khung dữ kiện, thêm Chỉ số tài chính, không đối chiếu hướng tăng giảm; cũng có nút Gặp môi giới."],
        ],
        reqs: ["REQ-HOI-DAP-017", "REQ-HOI-DAP-018", "REQ-HOI-DAP-019", "REQ-HOI-DAP-027"],
        notes: "Giá đóng cửa và hai bài tin là dữ liệu thật. Mọi số trong lời LLM (28/10, 4, 26/10, 900) đều có trong bài tin đưa vào, nên qua được bộ chặn số. Phần dữ kiện khối ngoại và cùng ngành được rút gọn trên slide.",
      },
      {
        level: "4", title: "Đèn giao thông & an toàn đầu ra",
        tagline: "Mỗi câu hỏi được xếp xanh, vàng hoặc đỏ. Câu xin ý kiến mua bán luôn vào nhánh đỏ và được chuyển cho người của APEC.",
        chat: [
          { u: "Có nên mua FPT không?" },
          { b: "🛡️ Mình không đưa ra ý kiến mua bán, rủi ro hay pháp lý. Đó là quyết định của riêng bạn và cần người có chuyên môn của APEC.\n\nDữ kiện mình có về FPT:\n• Giá hiện tại: 52.700 đ\n• Trong danh mục mô phỏng của bạn, FPT chiếm 16,4% (dữ liệu mô phỏng).\n\nNguồn: APEC, giá lúc 15:00 30/10/2026\nNếu cần ý kiến chuyên môn, bấm \"Gặp môi giới\" để nhờ người của APEC hỗ trợ.\nĐây là thông tin tham khảo, không phải khuyến nghị đầu tư.", kb: [RATE, ["*Gặp môi giới"]] },
          { tap: "Gặp môi giới" },
          { b: "Mình đã gửi yêu cầu gặp môi giới tới nhóm nội bộ. Đây là bản demo nên chưa có môi giới thật nhận nhé." },
        ],
        points: [
          ["Đỏ luôn thắng", "Câu vừa xin giải thích vừa xin ý kiến mua bán được xếp vào nhánh đỏ. Từ chối nhưng vẫn đưa dữ kiện có nguồn."],
          ["Chặn cụm từ cấm", "Lời LLM chứa \"nên mua\", \"giá mục tiêu\", \"sẽ tăng\"… thì cả câu trả lời bị thay bằng câu từ chối chuẩn."],
          ["Chặn số lạ", "Số trong lời LLM phải có trong câu hỏi hoặc dữ kiện; mỗi lần chặn được ghi Lỗi LLM để Quản trị viên xem."],
        ],
        reqs: ["REQ-PRODUCT-002", "REQ-HOI-DAP-002", "REQ-HOI-DAP-003", "REQ-HOI-DAP-005", "REQ-HOI-DAP-006", "REQ-HOI-DAP-022"],
        notes: "Thông điệp chính cho APEC: bot không thay môi giới, bot chuyển nhu cầu tư vấn về đúng người. Nút Gặp môi giới gửi câu hỏi vào nhóm nội bộ của APEC; bản demo chưa có môi giới thật trực.",
      },
      {
        level: "5", title: "Cảnh báo giá theo mức",
        tagline: "Đặt mức giá bằng một câu chat; bot đọc lại cách hiểu trước khi bật, quét mỗi 60 giây trong giờ giao dịch và báo đúng một lần.",
        chat: [
          { u: "Báo khi HPG xuống dưới 20.000" },
          { b: "Mình hiểu là: báo bạn khi HPG xuống dưới 20.000 đ. Bật cảnh báo này nhé?", kb: [["*Xác nhận", "Huỷ"]] },
          { tap: "Xác nhận" },
          { b: "Đã bật cảnh báo: HPG xuống dưới 20.000 đ. Mình chỉ quét giá trong giờ giao dịch (9:00 đến 15:00, thứ Hai đến thứ Sáu)." },
          { sys: "Trong phiên, giá HPG khớp 19.950 đ" },
          { b: "🔔 Cảnh báo giá: HPG xuống dưới 20.000 đ.\n\n• Giá hiện tại: 19.950 đ (10:15)\n\nNguồn: APEC, giá lúc 10:15 02/11/2026\nCảnh báo này đã tắt. Đặt lại không?", kb: [["Đặt lại", "Không"]] },
        ],
        points: [
          ["Đọc lại trước khi bật", "Bot nêu lại mã, hướng và mức giá; chưa bấm Xác nhận thì chưa có cảnh báo nào."],
          ["Một lần, đúng giờ", "Quét mỗi 60 giây chỉ trong giờ giao dịch thứ Hai đến thứ Sáu; gửi xong tự tắt, có nút Đặt lại."],
          ["Có trần", "Tối đa 10 Cảnh báo giá đang bật mỗi người. Đặt được bằng câu chat hoặc bằng nút gợi ý ±5%, ±10% trong menu."],
        ],
        reqs: ["REQ-DU-LIEU-THI-TRUONG-016", "REQ-DU-LIEU-THI-TRUONG-017", "REQ-DU-LIEU-THI-TRUONG-018"],
        notes: "Phần cảnh báo được gửi là minh hoạ một phiên giả định ngày 02/11/2026. Từ đây trở đi bot chủ động nhắn cho người dùng, không chờ họ hỏi.",
      },
      {
        level: "5", title: "Cảnh báo biến động giá",
        tagline: "Bot tự phát hiện mã đang theo dõi tăng hoặc giảm mạnh trong 15 phút, và nói rõ vì sao người này nhận được tin.",
        chat: [
          { u: "Báo khi FPT biến động 5%" },
          { b: "Mình hiểu là bạn muốn đặt cảnh báo biến động giá riêng: báo bạn khi FPT tăng hoặc giảm từ 5% trở lên, trong cửa sổ so sánh 15 phút, chạy trong giờ giao dịch. Bật cảnh báo này nhé?", kb: [["*Xác nhận", "Huỷ"]] },
          { tap: "Xác nhận" },
          { b: "Đã bật cảnh báo biến động: FPT tăng hoặc giảm từ 5% trở lên. Mình chỉ quét trong giờ giao dịch (9:00 đến 15:00, thứ Hai đến thứ Sáu)." },
          { sys: "Trong phiên, FPT tăng nhanh trong 15 phút" },
          { b: "📈 Cảnh báo biến động giá: FPT tăng 5,3% trong 15 phút.\n\n• Giá bây giờ: 55.500 đ (14:15)\n• 15 phút trước: 52.700 đ (14:00)\n• So với giá đóng cửa phiên trước (30/10, 52.700 đ): tăng 5,3%.\n\nVì sao mình báo: bạn theo dõi FPT qua cảnh báo biến động giá riêng đang bật.\nMuốn thôi nhận, huỷ Cảnh báo biến động giá riêng.\nNguồn: APEC, giá lúc 14:15 02/11/2026\nĐây là thông tin tham khảo, không phải khuyến nghị đầu tư." },
        ],
        points: [
          ["Mặc định 3%, tuỳ chỉnh 1–10%", "Người theo dõi mã qua danh mục, Đăng ký quan tâm hoặc Cảnh báo giá nhận ở ngưỡng 3%; ai đặt ngưỡng riêng thì theo ngưỡng riêng."],
          ["Nêu lý do nhận tin", "Mỗi cảnh báo nói người này theo dõi mã qua đường nào và cách thôi nhận."],
          ["Chống làm phiền", "Không gửi lại cùng mã, cùng hướng trong 60 phút; tối đa 10 cảnh báo biến động mỗi người mỗi ngày."],
        ],
        reqs: ["REQ-DU-LIEU-THI-TRUONG-019", "REQ-DU-LIEU-THI-TRUONG-020", "REQ-DU-LIEU-THI-TRUONG-021", "REQ-DU-LIEU-THI-TRUONG-022", "REQ-HOI-DAP-030"],
        notes: "Phần cảnh báo là minh hoạ một phiên giả định. Biến động so trên Ảnh chụp giá lưu mỗi 5 phút của ngày hôm nay, không so với dữ liệu cũ.",
      },
      {
        level: "5", title: "Đăng ký quan tâm & Bản tin",
        tagline: "Người dùng chọn công ty, người hay chủ đề muốn theo dõi; bot gom tin quan trọng thành Bản tin cực ngắn theo giờ người dùng chọn.",
        chat: [
          { u: "Báo tôi tin về HPG" },
          { b: "Đã đăng ký quan tâm HPG. Tin về đối tượng này sẽ đến trong Bản tin theo cách nhận bạn đã chọn; xem hoặc huỷ ở Menu chính, mục Tin tức quan tâm." },
          { tap: "Menu chính › Tin tức quan tâm › Xem danh sách" },
          { b: "Đăng ký quan tâm (1/20 đang bật):\n1. HPG (công ty) — mức tin: Cao\n\nCách nhận Bản tin: cữ giờ trong phiên.", kb: [["Đổi mức HPG"], ["Cữ giờ", "*Bản tin 15h", "Bản tin 18h"], ["Thêm", "Bỏ"]] },
          { tap: "Bản tin 15h" },
          { sys: "15:00 — bot gửi Bản tin cuối phiên" },
          { b: "📰 Bản tin cuối phiên 30/10/2026: 1 tin về đối tượng bạn quan tâm.\n\n⚡ HPG — Người thân lãnh đạo Hòa Phát bán thành công cổ phiếu như đăng ký · Giá: 21.000 đ\n   https://cafef.vn/nguoi-than-lanh-dao-hoa-phat-ban-thanh-cong-co-phieu-nhu-dang-ky-188261015141024258.chn" },
        ],
        points: [
          ["Một Bản tin thay cho nhiều tin lẻ", "Tin được gom vào Bản tin theo cữ giờ trong phiên, lúc 15h hoặc 18h; không có tin mới thì không gửi."],
          ["Tự chọn mức tin", "Mỗi đăng ký chọn mức tin thấp nhất Cao hoặc Trung bình; tin mức Thấp không bao giờ gửi."],
          ["Cực ngắn, có giá", "Mỗi mục 1–2 dòng kèm giá gần nhất của mã liên quan và link gốc. Tối đa 20 đăng ký mỗi người."],
        ],
        reqs: ["REQ-TIN-TUC-021", "REQ-TIN-TUC-022", "REQ-TIN-TUC-024", "REQ-TIN-TUC-025", "REQ-TIN-TUC-026", "REQ-TIN-TUC-028", "REQ-TIN-TUC-029"],
        notes: "Mọi tin, kể cả mức Cao, đều đi qua Bản tin theo cách nhận người dùng chọn: không có tin đẩy lẻ làm phiền. Bấm 'Bản tin 15h' để đổi cách nhận ngay trên danh sách.",
      },
      {
        level: "6", title: "Pipeline tin tức",
        tagline: "Từ 12 nguồn tin đến Đối tượng tin và Quan hệ: mỗi bài được LLM bóc tách một lần, gộp thành Sự kiện, xếp mức quan trọng, rồi chờ Hậu kiểm.",
        flow: [
          ["RSS", "Thu 12 nguồn", "CafeF, VnExpress, Vietstock, VnEconomy (trong nước và thế giới), HOSE, HNX, Fed, ECB, SEC. Tối đa 20 bài mới mỗi nguồn mỗi lượt; một nguồn lỗi không làm hỏng lượt thu."],
          ["LLM", "Bóc tách một lần mỗi bài", "Loại sự kiện, tóm tắt tiếng Việt, Đối tượng tin, điểm ba tiêu chí, Quan hệ. Lệch hình dạng nhỏ được sửa; bài lỗi thử lại tối đa 3 lần rồi bỏ."],
          ["12h", "Gộp thành Sự kiện", "Các bài cùng chuyện đăng trong 12 giờ và đủ giống nhau gộp thành một Sự kiện; mỗi Sự kiện chỉ báo một lần."],
          ["Mức", "Xếp Mức độ quan trọng", "11 Loại sự kiện trong cấu hình: 7 mức Cao (kết quả kinh doanh, cổ tức, thay đổi lãnh đạo…), 2 Trung bình, 2 Thấp."],
          ["Đối tượng", "Đối tượng tin & Quan hệ", "Công ty, người, ngành, vĩ mô; tên gọi khác được gộp. Quan hệ chỉ ghi khi bài nói rõ, thuộc 4 loại: gia đình, cổ đông, lãnh đạo, công ty mẹ/con."],
          ["Hậu kiểm", "Quản trị viên xem lại", "Đối tượng mới dùng được ngay và vào hàng chờ Hậu kiểm: Giữ, Gộp vào đối tượng khác, Bỏ, hoặc Tách một lần bot tự gộp sai."],
        ],
        chat: [
          { u: "Quản trị › Đối tượng tin › Hậu kiểm" },
          { b: "#531 Doãn Gia Cường (người, HPG, Phó Chủ tịch HĐQT), chưa hậu kiểm, 1 tin đã gắn.\nTên gọi khác: DGC, Doãn Gia Cường\nTin mới nhất đã gắn:\n- Người thân lãnh đạo Hòa Phát bán thành công cổ phiếu như đăng ký (CafeF, 14:53 15/10/2026), lý do: đối tượng mới\n  https://cafef.vn/nguoi-than-lanh-dao-hoa-phat-ban-thanh-cong-co-phieu-nhu-dang-ky-188261015141024258.chn", kb: [["Gộp vào…"], ["*Giữ", "Bỏ"]] },
          { tap: "Giữ" },
          { b: "Đã giữ Doãn Gia Cường (đã hậu kiểm)." },
        ],
        reqs: ["REQ-TIN-TUC-001…012", "REQ-TIN-TUC-013…019", "REQ-TIN-TUC-030"],
        footnote: "Số liệu ngày 30/10/2026: 3.837 bài tin đã lưu, 1.726 Đối tượng tin, 1.360 đối tượng đang chờ Hậu kiểm.",
        notes: "Tên gọi khác 'DGC' cũng là mã của Hoá chất Đức Giang: ví dụ tốt cho lý do cần Hậu kiểm. Pipeline chạy mỗi 15 phút trong tiến trình bot.",
      },
      {
        level: "6", title: "Màn Quản trị trong bot",
        tagline: "Quản trị viên duyệt người dùng, đọc Nhật ký, xem đánh giá và Lỗi LLM ngay trong Telegram.",
        chat: [
          { u: "Quản trị" },
          { b: "Quản trị: bạn muốn làm gì?\nDanh sách mã: 1518 mã, cập nhật 08:00 30/10/2026.", kb: [["*Chờ duyệt (1)", "Người dùng"], ["Nhật ký", "Đánh giá"], ["Đối tượng tin", "Lỗi LLM"], ["Xoá tất cả dữ liệu"]] },
          { b: "Yêu cầu đăng ký đang chờ:\n- Trần Thị Mai (876543210)", kb: [["*Duyệt Trần Thị Mai", "Từ chối Trần Thị Mai"]] },
          { b: "Đã duyệt Trần Thị Mai." },
          { tap: "Lỗi LLM" },
          { b: "Lỗi đầu ra LLM\n24 giờ qua:\n- Phân loại câu hỏi: đã sửa 1 (trường thừa 1)\n7 ngày qua:\n- Phân loại câu hỏi: đã sửa 1 (trường thừa 1)\n- Giải thích Nhánh vàng: lùi về dữ kiện thuần 1 (số lạ 1)\nBài tin chưa vào hệ thống: 1 đang thử lại, 1 đã bỏ." },
        ],
        points: [
          ["Không ai vào được khi chưa duyệt", "Người lạ chỉ thấy nút Đăng ký; mọi Quản trị viên được báo và duyệt hoặc từ chối bằng một chạm."],
          ["Nhật ký đủ để kiểm", "Mỗi câu trả lời ghi nhánh xanh/vàng/đỏ, Trích dẫn nguồn, dấu lỗi LLM và đánh giá 👍/👎 của người dùng."],
          ["Dữ liệu cá nhân", "Người dùng tự xoá dữ liệu của mình; Quản trị viên thu hồi quyền hoặc xoá toàn bộ sau khi xác nhận."],
        ],
        reqs: ["REQ-PRODUCT-001", "REQ-PRODUCT-003", "REQ-QUYEN-TRUY-CAP-014", "REQ-QUYEN-TRUY-CAP-015", "REQ-QUYEN-TRUY-CAP-016", "REQ-QUYEN-TRUY-CAP-017", "REQ-QUYEN-TRUY-CAP-018", "REQ-QUYEN-TRUY-CAP-019"],
        notes: "Tên người chờ duyệt và số Lỗi LLM là minh hoạ. Nhấn mạnh: chỉ người có id trong danh sách Quản trị viên mới mở được màn này; mỗi người dùng tối đa 50 tin nhắn tự do mỗi ngày.",
      },
      {
        level: "6", title: "Trang quản trị web",
        tagline: "Trang chỉ đọc chạy riêng trên máy vận hành: duyệt mọi bảng dữ liệu, xem sơ đồ quan hệ, Kho tài liệu đã cắt đoạn và tham số đang chạy.",
        screens: [
          ["/", "Danh mục bảng", "Mọi bảng kèm số dòng chính xác; bảng mới do migration thêm tự hiện."],
          ["/tables/:bảng", "Duyệt bảng", "Lọc, sắp xếp, tìm tự do, 50 dòng một trang; ô khoá ngoại thành liên kết; phân biệt rỗng, chuỗi rỗng, 0 và sai."],
          ["/subjects/:id", "Hồ sơ Đối tượng tin", "Tên gọi khác, các lần gộp, Quan hệ đã lưu và suy ra, sơ đồ quan hệ quanh đối tượng."],
          ["/subjects/:a/with/:b", "Bằng chứng quan hệ", "Mọi Quan hệ giữa hai đối tượng và mọi bài nhắc cả hai, kèm vai trò của từng bên."],
          ["/network", "Mạng cùng xuất hiện", "Các cặp đối tượng có từ 2 bài chung trong 30 ngày, có trần số đối tượng và số cạnh."],
          ["/documents", "Kho tài liệu", "Danh sách Tài liệu nguồn và nội dung từng đoạn đã cắt; không hiện embedding."],
          ["/parameters", "Tham số đang chạy", "File cấu hình đọc lại mỗi lần tải, các ngưỡng hành vi; biến môi trường chỉ hiện đã đặt hay chưa."],
        ],
        points: [
          ["Chỉ trên máy cục bộ", "Chỉ nghe ở 127.0.0.1 và từ chối yêu cầu có Host lạ trước khi chạy truy vấn nào."],
          ["Chỉ đọc đến tận database", "Mọi truy vấn chạy trong giao dịch chỉ đọc; phương thức ghi bị từ chối."],
          ["Độc lập với bot", "Tiến trình riêng: không gọi Telegram, không gọi LLM, không chạy migration."],
        ],
        reqs: ["REQ-TRANG-QUAN-TRI-WEB-001…022"],
        notes: "Trang không có đăng nhập, đây là quyết định cho giai đoạn thử (ngày 20/10/2026). Demo trực tiếp bằng `pnpm web` rồi mở trang /subjects của FPT để xem sơ đồ quan hệ.",
      },
    ];

    const deck = document.getElementById("deck");
    const esc = (s) => s.replace(/[&<>"]/g, (c) => ({ "&": "&amp;", "<": "&lt;", ">": "&gt;", '"': "&quot;" })[c]);
    const linkify = (s) => esc(s).replace(/(https?:\/\/\S+)/g, '<span class="link">$1</span>');
    const pad = (n) => String(n).padStart(2, "0");

    function renderChat(chat) {
      return chat.map((m) => {
        if (m.u !== undefined) return `<div class="msg user"><div class="bubble">${esc(m.u)}</div></div>`;
        if (m.tap !== undefined) return `<div class="tap">👆 Bấm: ${esc(m.tap)}</div>`;
        if (m.sys !== undefined) return `<div class="sys">⏱ ${esc(m.sys)}</div>`;
        const body = linkify(m.b).replace("{LLM}", m.llm ? `<span class="llm">${linkify(m.llm)}</span>` : "");
        const kb = (m.kb ?? []).map((row) =>
          `<div class="kb-row">${row.map((label) => {
            const hit = label.startsWith("*");
            return `<span class="kb-btn${hit ? " hit" : ""}">${esc(hit ? label.slice(1) : label)}</span>`;
          }).join("")}</div>`).join("");
        return `<div class="msg bot"><div class="bubble">${body}</div>${kb ? `<div class="kb">${kb}</div>` : ""}</div>`;
      }).join("");
    }

    function phone(chat, note = "") {
      return `<div class="phone">
        <div class="phone-head"><div class="avatar">AD</div><div><div class="name">APS Demo Bot</div><div class="status">bot</div></div>${note}</div>
        <div class="chat">${renderChat(chat)}</div>
      </div>`;
    }

    const points = (list) => list.map(([h, p], i) => `<div class="card"><h4><span class="n">${i + 1}</span>${esc(h)}</h4><p>${esc(p)}</p></div>`).join("");
    const reqs = (list) => `<div class="side-label">Yêu cầu trong PRD</div><div class="reqs">${list.map((r) => `<span class="req">${esc(r)}</span>`).join("")}</div>`;
    const levelOf = (key) => LEVELS.find((l) => l.key === key);

    function addSlide(html, notes) {
      const el = document.createElement("section");
      el.className = "slide";
      el.innerHTML = html;
      el.dataset.notes = notes ?? "";
      deck.appendChild(el);
      return el;
    }

    // 1. Trang bìa
    addSlide(`
      <div class="badges"><span class="badge">FPT × APEC Securities</span><span class="badge level">POC · Bot demo</span></div>
      <h1>APS Demo Bot<br><span>17 kịch bản tính năng</span></h1>
      <p class="lead">Trợ lý ảo hỗ trợ nhà đầu tư tra cứu dữ liệu thị trường, điểm tin đa nguồn và giải đáp nghiệp vụ APS — cam kết 100% trích dẫn nguồn, an toàn pháp lý.</p>
      <div class="stats">
        <div class="stat"><b>1.518 mã</b><span>toàn bộ cổ phiếu niêm yết (HOSE, HNX, UPCOM)</span></div>
        <div class="stat"><b>12 nguồn tin</b><span>báo chí tài chính uy tín & công bố thông tin sở HOSE/HNX</span></div>
        <div class="stat"><b>3.800+ bài tin</b><span>tự động thu thập, tóm tắt tiếng Việt & gộp sự kiện 12h</span></div>
        <div class="stat"><b>830+ DN · 19 ngành</b><span>hồ sơ công ty, phân loại ngành & tỷ trọng (FPT, HPG, Ngân hàng, BĐS...)</span></div>
        <div class="stat"><b>440+ lãnh đạo</b><span>nhận diện tên gọi, bí danh & số cổ phiếu (Cường Đô La, Bầu Đức...)</span></div>
        <div class="stat"><b style="color: #34d399">0 khuyến nghị</b><span>tuyệt đối không khuyên mua bán: chuyển tiếp môi giới APEC</span></div>
      </div>
    `, "Mở đầu: đây là Bot demo cho nhóm Người dùng thử. Giá là giá chậm, mọi câu trả lời đều có Trích dẫn nguồn. Số liệu trên slide lấy từ dữ liệu demo ngày 30/10/2026.").classList.add("title-slide");

    // 2. Lộ trình
    const indexOfScenario = new Map();
    SCENARIOS.forEach((s, i) => indexOfScenario.set(s, i + 2));
    addSlide(`
      <div class="slide-header">
        <div class="badges"><span class="badge">Menu</span></div>
        <h2 class="slide-title">Từ đơn giản đến phức tạp</h2>
        <p class="slide-subtitle">Sáu cấp độ, mỗi cấp thêm một lớp năng lực. Bấm vào một kịch bản để nhảy tới slide đó.</p>
      </div>
      <div class="levels">${LEVELS.map((l) => `
        <div class="level-card"><h3>${esc(l.name)}</h3><div class="why">${esc(l.why)}</div><ol>${
          SCENARIOS.filter((s) => s.level === l.key).map((s) => `<li onclick="go(${indexOfScenario.get(s)})"><span class="num">${pad(SCENARIOS.indexOf(s) + 1)}</span>${esc(s.title)}</li>`).join("")
        }</ol></div>`).join("")}
      </div>
    `, "Đi lần lượt theo cấp. Nếu thời gian ngắn, chọn mỗi cấp một kịch bản: Hỏi giá, Kho tài liệu, Nhân vật, Đèn giao thông, Cảnh báo biến động, Màn Quản trị.");

    // 3. Các kịch bản
    SCENARIOS.forEach((s, i) => {
      const lvl = levelOf(s.level);
      const header = `
        <div class="slide-header">
          <div class="badges"><span class="badge">Kịch bản ${pad(i + 1)} / ${pad(SCENARIOS.length)}</span><span class="badge level">${esc(lvl.name)}</span></div>
          <h2 class="slide-title">${esc(s.title)}</h2>
          <p class="slide-subtitle">${esc(s.tagline)}</p>
        </div>`;
      const legend = s.chat && s.chat.some((m) => m.llm) ? `<div class="legend"><i></i>Viền tím: phần do LLM viết, đã qua bộ chặn</div>` : "";
      let left, right;
      if (s.screens) {
        left = `<div class="side"><div class="side-label">Các trang</div><div class="screens">${s.screens.map(([path, name, desc]) => `<div class="screen"><code>${esc(path)}</code><b>${esc(name)}</b><p>${esc(desc)}</p></div>`).join("")}</div></div>`;
        right = `<div class="side"><div class="side-label">Vì sao an toàn</div>${points(s.points)}${reqs(s.reqs)}</div>`;
      } else if (s.flow) {
        left = `<div class="side">${phone(s.chat)}</div>`;
        right = `<div class="side"><div class="side-label">Luồng xử lý một bài tin</div><div class="flow">${s.flow.map(([, h, p], k) => `<div class="flow-step"><div class="dot">${k + 1}</div><div class="body"><b>${esc(h)}</b><p>${esc(p)}</p></div></div>`).join("")}</div>${reqs(s.reqs)}${s.footnote ? `<div class="footnote">${esc(s.footnote)}</div>` : ""}</div>`;
      } else {
        left = `<div class="side">${phone(s.chat, legend)}</div>`;
        right = `<div class="side"><div class="side-label">Vì sao đáng tin</div>${points(s.points)}${reqs(s.reqs)}</div>`;
      }
      addSlide(`${header}<div class="scenario"${s.screens ? ' style="grid-template-columns: 1.4fr 1fr"' : ""}>${left}${right}</div>`, s.notes);
    });

    // 4. Tổng kết
    addSlide(`
      <div class="slide-header">
        <div class="badges"><span class="badge">Tổng kết</span></div>
        <h2 class="slide-title">Ba nguyên tắc xuyên suốt 17 kịch bản</h2>
        <p class="slide-subtitle">Mỗi nguyên tắc là một yêu cầu trong PRD, có test tự động và được ghi Nhật ký để kiểm lại.</p>
      </div>
      <div class="principles">
        <div class="principle p-green"><h3>Mọi số đều có nguồn</h3><p>Giá, chỉ số, tin, tài liệu: câu trả lời nêu nguồn và giờ hoặc ngày cập nhật. Thiếu dữ liệu thì nói thiếu, không bịa và không im lặng.</p></div>
        <div class="principle p-yellow"><h3>Code tính, LLM diễn đạt</h3><p>Dữ kiện do code tính. Số nào trong lời LLM không có trong dữ kiện bị chặn; vi phạm lần hai thì trả dữ kiện thuần.</p></div>
        <div class="principle p-red"><h3>Không khuyến nghị mua bán</h3><p>Câu xin ý kiến mua bán, rủi ro, pháp lý vào nhánh đỏ và chuyển cho người của APEC bằng nút Gặp môi giới.</p></div>
      </div>
      <div style="margin-top: 24px" class="card">
        <h4>Ngoài phạm vi Bot demo</h4>
        <p>Giá thời gian thực, tài khoản giao dịch thật (mọi danh mục là Khách mô phỏng), môi giới thật nhận yêu cầu, APF và các sản phẩm đầu tư khác của APEC.</p>
      </div>
    `, "Kết: nhắc lại ba nguyên tắc, rồi mời APEC chọn hướng cho giai đoạn tiếp theo (môi giới thật nhận yêu cầu, dữ liệu tài khoản thật, mở rộng Kho tài liệu).");

    // Điều hướng
    const slides = [...deck.querySelectorAll(".slide")];
    const counter = document.getElementById("counter");
    const progress = document.getElementById("progress-bar");
    const notesPanel = document.getElementById("notes-panel");
    const notesContent = document.getElementById("notes-content");
    let current = Math.min(Math.max(parseInt(location.hash.slice(1), 10) - 1 || 0, 0), slides.length - 1);

    function go(i) {
      if (i < 0 || i >= slides.length) return;
      current = i;
      slides.forEach((s, k) => {
        const active = k === i;
        s.classList.toggle("active", active);
        if (active) s.scrollTop = 0;
      });
      counter.textContent = `Slide ${pad(i + 1)} / ${pad(slides.length)}`;
      progress.style.width = `${(i / (slides.length - 1)) * 100}%`;
      notesContent.textContent = slides[i].dataset.notes || "Không có ghi chú cho slide này.";
      history.replaceState(null, "", `#${i + 1}`);
    }
    const toggleNotes = () => notesPanel.classList.toggle("open");
    function toggleFullScreen() {
      if (!document.fullscreenElement) document.documentElement.requestFullscreen().catch(() => {});
      else document.exitFullscreen().catch(() => {});
    }
    document.addEventListener("keydown", (e) => {
      const keys = {
        ArrowRight: () => go(current + 1), " ": () => go(current + 1), PageDown: () => go(current + 1),
        ArrowLeft: () => go(current - 1), PageUp: () => go(current - 1),
        Home: () => go(0), End: () => go(slides.length - 1),
        n: toggleNotes, N: toggleNotes, f: toggleFullScreen, F: toggleFullScreen,
      };
      if (keys[e.key]) { e.preventDefault(); keys[e.key](); }
    });
    // Hội thoại dài: thu nhỏ chữ trong khung chat cho vừa màn hình (không nhỏ hơn 10,5px) thay vì cuộn.
    function fitChats() {
      for (const chat of deck.querySelectorAll(".chat")) {
        let size = 13;
        chat.style.fontSize = `${size}px`;
        while (chat.scrollHeight > chat.clientHeight + 1 && size > 9.5) {
          size -= 0.5;
          chat.style.fontSize = `${size}px`;
        }
      }
    }
    fitChats();
    window.addEventListener("resize", fitChats);
    go(current);
  </script>
</body>
</html>
