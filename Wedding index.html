<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <title>排座助手 Pro - 6+4 智慧連續編號版</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        .canvas-bg { background-image: radial-gradient(#cbd5e1 1px, transparent 1px); background-size: 20px 20px; }
        .modal { display: none; position: fixed; inset: 0; background: rgba(0,0,0,0.6); align-items: center; justify-content: center; z-index: 50; backdrop-filter: blur(4px); }
        .modal.active { display: flex; }
        .table-circle { transition: all 0.2s; border: 4px solid white; box-shadow: 0 4px 10px rgba(0,0,0,0.1); }
        .table-circle:hover { transform: scale(1.05); border-color: #6366f1; }
        .selected-guest { border: 2px solid #4f46e5 !important; background-color: #eef2ff !important; box-shadow: 0 0 10px rgba(79, 70, 229, 0.2); }
        .aisle-text { writing-mode: vertical-lr; letter-spacing: 0.8em; opacity: 0.3; }
        .group-label { font-size: 10px; color: #94a3b8; font-weight: 800; letter-spacing: 0.1em; text-transform: uppercase; }
    </style>
</head>
<body class="bg-slate-50 h-screen flex flex-col overflow-hidden text-slate-800">

    <header class="bg-white border-b px-6 py-3 flex justify-between items-center shadow-sm z-20">
        <div class="flex items-center gap-4">
            <h1 class="text-xl font-black text-indigo-600 tracking-tighter">WEDDING SEATING</h1>
            <span class="bg-indigo-100 text-indigo-600 text-[10px] px-2 py-0.5 rounded-full font-bold">V3.4 PRO</span>
        </div>
        <div class="flex gap-2">
            <button onclick="addNewTable()" class="bg-white border border-indigo-200 text-indigo-600 px-4 py-1.5 rounded-lg text-sm font-bold hover:bg-indigo-50">＋新增一桌</button>
            <button onclick="toggleModal('guest-modal')" class="bg-white border px-4 py-1.5 rounded-lg text-sm font-bold hover:bg-slate-50">＋管理賓客</button>
            <button onclick="generateExportData()" class="bg-indigo-600 text-white px-4 py-1.5 rounded-lg text-sm font-bold shadow-md hover:bg-indigo-700">📊 匯出報告</button>
            <button onclick="resetApp()" class="text-red-400 hover:text-red-600 text-xs px-2 font-bold">重置</button>
        </div>
    </header>

    <main class="flex flex-1 overflow-hidden">
        <aside class="w-64 bg-white border-r flex flex-col shadow-lg">
            <div class="p-4 border-b bg-slate-50 flex justify-between items-center">
                <span class="font-bold text-xs uppercase text-slate-500">待分配賓客</span>
                <span id="unassigned-count" class="bg-slate-200 text-slate-600 text-[10px] px-2 py-0.5 rounded-full font-black">0</span>
            </div>
            <div id="guest-list" class="flex-1 overflow-y-auto p-3 space-y-2"></div>
        </aside>

        <section class="flex-1 relative canvas-bg bg-slate-100 p-8 overflow-auto">
            <div id="table-canvas" class="flex flex-col items-center min-w-[1000px]">
                <div class="w-full flex flex-col items-center mb-12">
                    <div class="bg-slate-800 text-white px-12 py-1.5 rounded-b-xl mb-10 text-[10px] font-black tracking-[0.5em] uppercase">STAGE 舞台中心</div>
                    <div id="main-table-container"></div>
                </div>

                <div class="flex justify-center gap-12">
                    <div class="flex flex-col items-center">
                        <div class="group-label mb-4">左側前方 (1-6)</div>
                        <div id="left-6" class="grid grid-cols-2 gap-6 p-4 bg-slate-200/30 rounded-2xl"></div>
                        <div class="h-16 flex items-center justify-center italic text-slate-300 font-bold text-xs">── 走道 ──</div>
                        <div class="group-label mb-4">左側後方 (7+)</div>
                        <div id="left-4" class="grid grid-cols-2 gap-6 p-4 bg-slate-200/30 rounded-2xl"></div>
                    </div>
                    <div class="flex flex-col items-center pt-20">
                        <div class="aisle-text text-slate-300 font-black text-sm uppercase opacity-50">紅毯進場通道</div>
                    </div>
                    <div class="flex flex-col items-center">
                        <div class="group-label mb-4">右側前方 (1-6)</div>
                        <div id="right-6" class="grid grid-cols-2 gap-6 p-4 bg-slate-200/30 rounded-2xl"></div>
                        <div class="h-16 flex items-center justify-center italic text-slate-300 font-bold text-xs">── 走道 ──</div>
                        <div class="group-label mb-4">右側後方 (7+)</div>
                        <div id="right-4" class="grid grid-cols-2 gap-6 p-4 bg-slate-200/30 rounded-2xl"></div>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <div id="guest-modal" class="modal"><div class="bg-white rounded-2xl shadow-2xl w-[400px] p-6">
        <h3 class="font-bold mb-4">匯入賓客名單</h3>
        <textarea id="guest-input" rows="8" class="w-full border p-4 rounded-xl text-sm bg-slate-50 outline-none" placeholder="姓名，一人一行..."></textarea>
        <div class="flex justify-end mt-4 gap-2"><button onclick="toggleModal('guest-modal')" class="px-4">取消</button><button onclick="addGuests()" class="bg-slate-900 text-white px-8 py-2 rounded-xl font-bold">加入</button></div>
    </div></div>

    <div id="detail-modal" class="modal"><div class="bg-white rounded-2xl shadow-2xl w-[350px] p-6 text-center">
        <h3 id="dt-name" class="font-black text-xl mb-4 text-indigo-600"></h3>
        <div id="dt-list" class="space-y-2 mb-6 max-h-64 overflow-y-auto text-left"></div>
        <div id="dt-delete-area" class="border-t pt-4"></div>
        <button onclick="toggleModal('detail-modal')" class="w-full bg-slate-200 py-2 rounded-xl mt-4 font-bold text-xs">關閉</button>
    </div></div>

    <div id="export-modal" class="modal"><div class="bg-white rounded-2xl shadow-2xl w-[500px] p-6">
        <h3 class="font-bold mb-4 italic text-indigo-600">📊 最終清單匯出</h3>
        <textarea id="export-text" rows="10" class="w-full border p-3 rounded-xl text-xs font-mono bg-slate-50 mb-4" readonly></textarea>
        <button onclick="toggleModal('export-modal')" class="w-full bg-indigo-600 text-white py-2 rounded-xl font-bold">關閉</button>
    </div></div>

    <script>
        let guests = [];
        let tables = [];
        let selectedId = null;
        const KEY = 'WEDDING_V3_4_64';

        function toggleModal(id) { document.getElementById(id).classList.toggle('active'); }

        // --- 核心邏輯：自動重新編號 ---
        function reorderTables() {
            let guestTableCount = 1;
            tables.forEach(t => {
                if (t.id !== 'main') {
                    t.name = `第 ${guestTableCount} 桌`;
                    // 根據序號分配區域 (6+4 邏輯)
                    if (guestTableCount <= 6) t.section = 'L6';
                    else if (guestTableCount <= 12) t.section = 'R6';
                    else if (guestTableCount <= 16) t.section = 'L4';
                    else t.section = 'R4';
                    guestTableCount++;
                }
            });
        }

        function initTables() {
            tables = [{ id: 'main', name: "👑 主桌", cap: 12, list: [], section: 'main' }];
            for (let i = 1; i <= 20; i++) {
                tables.push({ id: 't'+Date.now()+i, name: `第 ${i} 桌`, cap: 10, list: [], section: '' });
            }
            reorderTables();
        }

        function addNewTable() {
            tables.push({ id: 't'+Date.now(), name: "", cap: 10, list: [], section: '' });
            reorderTables();
            render();
        }

        function deleteTable(tid) {
            if (tid === 'main') return alert("主桌不能刪除！");
            if (confirm("刪除此桌？賓客將回到名單。")) {
                const idx = tables.findIndex(x => x.id === tid);
                tables[idx].list.forEach(g => guests.find(x => x.id === g.id).tId = null);
                tables.splice(idx, 1);
                reorderTables();
                toggleModal('detail-modal');
                render();
            }
        }

        function addGuests() {
            const input = document.getElementById('guest-input');
            input.value.split('\n').filter(n => n.trim()).forEach(name => {
                guests.push({ id: Math.random(), name: name.trim(), tId: null });
            });
            input.value = ''; toggleModal('guest-modal'); render();
        }

        function render() {
            const gList = document.getElementById('guest-list');
            const unassigned = guests.filter(g => !g.tId);
            gList.innerHTML = unassigned.map(g => `
                <div onclick="selectedId = (selectedId === ${g.id} ? null : ${g.id}); render();" class="p-3 bg-white border rounded-xl cursor-pointer text-sm font-bold shadow-sm ${selectedId === g.id ? 'selected-guest' : ''}">
                    ${g.name}
                </div>
            `).join('') || '<p class="text-slate-300 text-center py-10 text-xs italic">無待分配賓客</p>';
            document.getElementById('unassigned-count').innerText = unassigned.length;

            ['main-table-container','left-6','left-4','right-6','right-4'].forEach(id => document.getElementById(id).innerHTML = '');

            tables.forEach(t => {
                const div = document.createElement('div');
                div.className = `table-circle w-28 h-28 rounded-full bg-white flex flex-col items-center justify-center cursor-pointer relative ${t.section === 'main' ? 'w-36 h-36 border-amber-400 bg-amber-50' : 'border-slate-100'}`;
                div.innerHTML = `<span class="text-[8px] font-black text-slate-300">${t.name}</span><span class="text-lg font-black">${t.list.length}<span class="text-xs text-slate-300">/${t.cap}</span></span><div class="text-[7px] text-slate-400 font-bold truncate w-20 text-center">${t.list.map(x=>x.name).join(',')}</div>`;
                div.onclick = () => handleTable(t.id);

                const container = { 'main': 'main-table-container', 'L6': 'left-6', 'L4': 'left-4', 'R6': 'right-6', 'R4': 'right-4' }[t.section];
                if(container) document.getElementById(container).appendChild(div);
            });
            localStorage.setItem(KEY, JSON.stringify({ guests, tables }));
        }

        function handleTable(tid) {
            const t = tables.find(x => x.id === tid);
            if (selectedId) {
                const g = guests.find(x => x.id === selectedId);
                if (t.list.length < t.cap) { t.list.push({ id: g.id, name: g.name }); g.tId = tid; selectedId = null; render(); }
                else alert("已滿！");
            } else {
                document.getElementById('dt-name').innerText = t.name;
                document.getElementById('dt-list').innerHTML = t.list.map(g => `<div class="flex justify-between p-2 bg-slate-50 rounded-lg mb-1 text-sm"><span>${g.name}</span><button onclick="removeG('${t.id}', ${g.id})" class="text-red-500 font-bold">移除</button></div>`).join('') || '<p class="text-center text-slate-300 py-4 text-xs">尚無賓客</p>';
                document.getElementById('dt-delete-area').innerHTML = t.id !== 'main' ? `<button onclick="deleteTable('${t.id}')" class="text-red-400 text-[10px] font-bold hover:underline">🗑️ 刪除此桌並自動重編號</button>` : '';
                toggleModal('detail-modal');
            }
        }

        function removeG(tid, gid) {
            const t = tables.find(x => x.id === tid);
            t.list = t.list.filter(x => x.id !== gid);
            guests.find(x => x.id === gid).tId = null;
            toggleModal('detail-modal'); render();
        }

        function generateExportData() {
            let res = "【婚禮座位分配報告】\n\n";
            tables.forEach(t => res += `${t.name}: ${t.list.map(x=>x.name).join('、') || '空'}\n`);
            document.getElementById('export-text').value = res;
            toggleModal('export-modal');
        }

        function resetApp() { if(confirm("確定重置嗎？")) { localStorage.removeItem(KEY); location.reload(); } }

        window.onload = () => {
            const saved = localStorage.getItem(KEY);
            if (saved) { const p = JSON.parse(saved); guests = p.guests; tables = p.tables; } 
            else initTables();
            render();
        };
    </script>
</body>
</html>
