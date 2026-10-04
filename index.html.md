<!DOCTYPE html>

<html lang="th">

<head>

&#x20;   <meta charset="UTF-8">

&#x20;   <meta name="viewport" content="width=device-width, initial-scale=1.0">

&#x20;   <title>WINTERFAT - Member Directory</title>

&#x20;   <script src="https://cdn.tailwindcss.com"></script>

&#x20;   <link rel="preconnect" href="https://fonts.googleapis.com">

&#x20;   <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>

&#x20;   <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;600;700;800;900\&display=swap" rel="stylesheet">

&#x20;   <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">



&#x20;   <script>

&#x20;       tailwind.config = {

&#x20;           theme: {

&#x20;               extend: {

&#x20;                   colors: {

&#x20;                       gold: {

&#x20;                           light: '#fbf0b9',

&#x20;                           DEFAULT: '#d4af37',

&#x20;                           dark: '#aa7c11',

&#x20;                       },

&#x20;                       brandRed: {

&#x20;                           DEFAULT: '#ff3344',

&#x20;                           glow: 'rgba(255, 51, 68, 0.4)',

&#x20;                       }

&#x20;                   },

&#x20;                   fontFamily: {

&#x20;                       montserrat: \['Montserrat', 'sans-serif'],

&#x20;                   }

&#x20;               }

&#x20;           }

&#x20;       }

&#x20;   </script>



&#x20;   <style>

&#x20;       body {

&#x20;           background-color: #050507;

&#x20;           color: #e2e8f0;

&#x20;           font-family: 'Montserrat', sans-serif;

&#x20;           overflow-x: hidden;

&#x20;       }



&#x20;       .luxury-card {

&#x20;           background: rgba(18, 18, 22, 0.92);

&#x20;           backdrop-filter: blur(12px);

&#x20;           border: 1.5px solid rgba(255, 60, 60, 0.35);

&#x20;           box-shadow: 0 0 15px rgba(255, 40, 40, 0.08), inset 0 0 15px rgba(0, 0, 0, 0.5);

&#x20;           transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);

&#x20;       }



&#x20;       .luxury-card:hover {

&#x20;           border-color: rgba(255, 75, 75, 0.8);

&#x20;           box-shadow: 0 0 25px rgba(255, 50, 50, 0.25), 0 8px 25px rgba(0, 0, 0, 0.6);

&#x20;           transform: translateY(-2px);

&#x20;       }



&#x20;       .watermark-text {

&#x20;           position: fixed;

&#x20;           top: 45%;

&#x20;           left: 50%;

&#x20;           transform: translate(-50%, -50%) rotate(-6deg);

&#x20;           font-size: 16vw;

&#x20;           font-weight: 900;

&#x20;           color: rgba(255, 255, 255, 0.025);

&#x20;           white-space: nowrap;

&#x20;           pointer-events: none;

&#x20;           user-select: none;

&#x20;           z-index: 0;

&#x20;           font-family: 'Montserrat', sans-serif;

&#x20;           text-transform: uppercase;

&#x20;           letter-spacing: 0.05em;

&#x20;       }



&#x20;       #particles-canvas {

&#x20;           position: fixed;

&#x20;           top: 0;

&#x20;           left: 0;

&#x20;           width: 100%;

&#x20;           height: 100%;

&#x20;           pointer-events: none;

&#x20;           z-index: 0;

&#x20;       }



&#x20;       .search-input {

&#x20;           background: rgba(15, 15, 18, 0.95);

&#x20;           border: 1px solid rgba(255, 255, 255, 0.18);

&#x20;           box-shadow: inset 0 2px 4px rgba(0, 0, 0, 0.8), 0 0 10px rgba(0,0,0,0.5);

&#x20;           transition: all 0.3s ease;

&#x20;       }



&#x20;       .search-input:focus {

&#x20;           border-color: rgba(212, 175, 55, 0.7);

&#x20;           box-shadow: 0 0 18px rgba(212, 175, 55, 0.25), inset 0 2px 4px rgba(0, 0, 0, 0.9);

&#x20;           outline: none;

&#x20;       }



&#x20;       .ig-btn {

&#x20;           background: linear-gradient(45deg, #f09433 0%, #e6683c 25%, #dc2743 50%, #cc2366 75%, #bc1888 100%);

&#x20;           border: 1px solid rgba(220, 39, 67, 0.5);

&#x20;           box-shadow: 0 0 12px rgba(220, 39, 67, 0.3);

&#x20;       }



&#x20;       .ig-btn:hover {

&#x20;           box-shadow: 0 0 18px rgba(220, 39, 67, 0.6);

&#x20;           filter: brightness(1.1);

&#x20;       }



&#x20;       ::-webkit-scrollbar {

&#x20;           width: 6px;

&#x20;       }

&#x20;       ::-webkit-scrollbar-track {

&#x20;           background: #050507;

&#x20;       }

&#x20;       ::-webkit-scrollbar-thumb {

&#x20;           background: #22222a;

&#x20;           border-radius: 3px;

&#x20;       }

&#x20;       ::-webkit-scrollbar-thumb:hover {

&#x20;           background: #d4af37;

&#x20;       }

&#x20;   </style>

</head>

<body class="min-h-screen relative flex flex-col items-center pb-12">



&#x20;   <canvas id="particles-canvas"></canvas>

&#x20;   <div class="watermark-text">WINTERFAT</div>



&#x20;   <!-- Main Container -->

&#x20;   <main class="relative z-10 w-full max-w-xl px-4 sm:px-6 pt-3 flex flex-col items-center">



&#x20;       <!-- Top Action Bar \& Founder Permission Lock -->

&#x20;       <div class="w-full flex justify-between items-center mb-2 gap-2 flex-wrap sm:flex-nowrap">

&#x20;           <div id="addBtnContainer">

&#x20;               <button id="addMemberBtn" onclick="openAddModal()" class="text-\[11px] font-bold text-black bg-gold hover:bg-yellow-300 flex items-center gap-1.5 px-3 py-1.5 rounded-lg border border-gold transition shadow-lg opacity-50 cursor-not-allowed">

&#x20;                   <i class="fa-solid fa-user-plus text-\[10px]"></i>

&#x20;                   <span>Add Member</span>

&#x20;               </button>

&#x20;           </div>



&#x20;           <!-- สวิตช์เปิดสิทธิ์ยศสูงสุดแบบมีระบบยืนยันตัวตน -->

&#x20;           <div class="flex items-center gap-2 bg-zinc-900/90 border border-zinc-800 px-3 py-1.5 rounded-xl">

&#x20;               <span class="text-\[10px] sm:text-\[11px] font-bold tracking-wider text-gray-300 flex items-center gap-1">

&#x20;                   👑 <span id="founderStatusText" class="text-gray-400">Founder View Only</span>

&#x20;               </span>

&#x20;               <label class="relative inline-flex items-center cursor-pointer">

&#x20;                   <input type="checkbox" id="founderToggle" onchange="toggleFounderAccess(this.checked)" class="sr-only peer">

&#x20;                   <div class="w-8 h-4 bg-zinc-700 peer-focus:outline-none rounded-full peer peer-checked:after:translate-x-full peer-checked:after:border-white after:content-\[''] after:absolute after:top-\[2px] after:left-\[2px] after:bg-white after:border-gray-300 after:border after:rounded-full after:h-3 after:w-3 after:transition-all peer-checked:bg-gold"></div>

&#x20;               </label>

&#x20;           </div>



&#x20;           <button onclick="resetDefaultData()" title="รีเซ็ตคืนค่าเริ่มต้น" class="text-\[11px] text-gray-400 hover:text-red-400 flex items-center gap-1.5 bg-zinc-900/80 px-2.5 py-1.5 rounded-lg border border-zinc-800 transition">

&#x20;               <i class="fa-solid fa-rotate-left text-\[10px]"></i>

&#x20;               <span class="hidden sm:inline">รีเซ็ต</span>

&#x20;           </button>

&#x20;       </div>



&#x20;       <header class="flex flex-col items-center text-center mb-2 w-full">

&#x20;           <div id="logoContainer" class="relative flex flex-col items-center justify-center">

&#x20;               <img id="mainLogoImg" 

&#x20;                    src="https://cdn.discordapp.com/attachments/1366695429403840534/1483473595173830719/Crowned\_cheeseburger\_with\_motivational\_vibes.png?ex=6ac30cb2\&is=6ac1bb32\&hm=45807ef5a238af63d0373cdff6939f80bc79b3f05f053479d1f386fc49be5c0e\&" 

&#x20;                    alt="WINTERFAT Logo" 

&#x20;                    class="w-full max-w-\[200px] sm:max-w-\[240px] h-auto object-contain drop-shadow-\[0\_4px\_16px\_rgba(0,0,0,0.9)] transition-all duration-300">

&#x20;           </div>

&#x20;       </header>



&#x20;       <section class="w-full mb-4 space-y-2.5">

&#x20;           <!-- Search Bar -->

&#x20;           <div class="relative w-full">

&#x20;               <input 

&#x20;                   type="text" 

&#x20;                   id="searchInput"

&#x20;                   placeholder="SEARCH MEMBERS..." 

&#x20;                   class="search-input w-full py-2.5 sm:py-3 px-5 rounded-full text-center text-xs sm:text-sm tracking-\[0.2em] font-bold text-white placeholder-gray-500 uppercase"

&#x20;               >

&#x20;               <div class="absolute right-4 top-1/2 -translate-y-1/2 text-gray-400 pointer-events-none">

&#x20;                   <i class="fa-solid fa-magnifying-glass text-gold text-xs sm:text-sm"></i>

&#x20;               </div>

&#x20;           </div>



&#x20;           <!-- Filter Categories -->

&#x20;           <div class="flex items-center justify-center gap-1.5 flex-wrap" id="filterContainer">

&#x20;               <button onclick="filterRole('ALL')" class="filter-btn active-filter px-2.5 sm:px-3 py-1 rounded-full text-\[10px] sm:text-\[11px] font-bold tracking-wider uppercase transition-all duration-300 bg-gold text-black border border-gold shadow-\[0\_0\_10px\_rgba(212,175,55,0.4)]">

&#x20;                   ALL (<span id="count-all">0</span>)

&#x20;               </button>

&#x20;               <button onclick="filterRole('FOUNDERS')" class="filter-btn px-2.5 sm:px-3 py-1 rounded-full text-\[10px] sm:text-\[11px] font-bold tracking-wider uppercase transition-all duration-300 bg-zinc-900/90 text-gray-400 border border-zinc-800 hover:border-red-500/50 hover:text-white">

&#x20;                   👑 FOUNDERS (<span id="count-founders">0</span>)

&#x20;               </button>

&#x20;               <button onclick="filterRole('ADMIN')" class="filter-btn px-2.5 sm:px-3 py-1 rounded-full text-\[10px] sm:text-\[11px] font-bold tracking-wider uppercase transition-all duration-300 bg-zinc-900/90 text-gray-400 border border-zinc-800 hover:border-gold/50 hover:text-white">

&#x20;                   ⭐ ADMIN (<span id="count-admin">0</span>)

&#x20;               </button>

&#x20;               <button onclick="filterRole('VIP')" class="filter-btn px-2.5 sm:px-3 py-1 rounded-full text-\[10px] sm:text-\[11px] font-bold tracking-wider uppercase transition-all duration-300 bg-zinc-900/90 text-gray-400 border border-zinc-800 hover:border-purple-500/50 hover:text-white">

&#x20;                   💎 VIP (<span id="count-vip">0</span>)

&#x20;               </button>

&#x20;               <button onclick="filterRole('MEMBER')" class="filter-btn px-2.5 sm:px-3 py-1 rounded-full text-\[10px] sm:text-\[11px] font-bold tracking-wider uppercase transition-all duration-300 bg-zinc-900/90 text-gray-400 border border-zinc-800 hover:border-sky-500/50 hover:text-white">

&#x20;                   👤 MEMBER (<span id="count-member">0</span>)

&#x20;               </button>

&#x20;           </div>

&#x20;       </section>



&#x20;       <section id="memberList" class="w-full space-y-3">

&#x20;           <!-- Dynamic Member Cards -->

&#x20;       </section>



&#x20;       <div id="noResults" class="hidden text-center py-8 text-gray-500 font-medium">

&#x20;           <i class="fa-solid fa-utensils text-2xl mb-2 text-zinc-700"></i>

&#x20;           <p class="tracking-wider uppercase text-xs">ไม่พบรายชื่อสมาชิกตรงกับคำค้นหา</p>

&#x20;       </div>



&#x20;   </main>



&#x20;   <!-- Modal ยืนยันรหัสผ่าน Founder Access -->

&#x20;   <div id="passwordModal" class="fixed inset-0 bg-black/85 backdrop-blur-md z-50 flex items-center justify-center p-4 hidden">

&#x20;       <div class="bg-zinc-900 border border-gold/60 rounded-2xl w-full max-w-sm p-5 shadow-2xl relative">

&#x20;           <h2 class="text-sm font-bold text-gold uppercase tracking-wider mb-2 flex items-center gap-2">

&#x20;               <i class="fa-solid fa-lock text-gold"></i> ยืนยันสิทธิ์ยศสูงสุด (FOUNDER)

&#x20;           </h2>

&#x20;           <p class="text-xs text-gray-400 mb-4">กรุณากรอกรหัสผ่านเพื่อเปิดใช้งานระบบการจัดการสมาชิก</p>



&#x20;           <form onsubmit="verifyFounderPassword(event)" class="space-y-3">

&#x20;               <div>

&#x20;                   <input type="password" id="founderPasswordInput" placeholder="กรอกรหัสผ่าน" class="w-full bg-black/60 border border-zinc-700 rounded-lg px-3 py-2 text-xs text-white focus:outline-none focus:border-gold">

&#x20;                   <p id="passwordError" class="text-\[11px] text-red-500 mt-1 hidden">รหัสผ่านไม่ถูกต้อง!</p>

&#x20;               </div>



&#x20;               <div class="pt-2 flex justify-end gap-2 border-t border-zinc-800">

&#x20;                   <button type="button" onclick="cancelPasswordModal()" class="px-3.5 py-1.5 rounded-lg text-xs font-bold text-gray-400 bg-zinc-800 hover:bg-zinc-700 transition">ยกเลิก</button>

&#x20;                   <button type="submit" class="px-4 py-1.5 rounded-lg text-xs font-bold text-black bg-gold hover:bg-yellow-400 transition">ยืนยันรหัส</button>

&#x20;               </div>

&#x20;           </form>

&#x20;       </div>

&#x20;   </div>



&#x20;   <!-- Modal เปลี่ยนรูปโปรไฟล์สำหรับผู้ใช้ทั่วไป -->

&#x20;   <div id="avatarModal" class="fixed inset-0 bg-black/85 backdrop-blur-md z-50 flex items-center justify-center p-4 hidden">

&#x20;       <div class="bg-zinc-900 border border-gold/50 rounded-2xl w-full max-w-sm p-5 shadow-2xl relative">

&#x20;           <button onclick="closeAvatarModal()" class="absolute top-4 right-4 text-gray-400 hover:text-white text-base">

&#x20;               <i class="fa-solid fa-xmark"></i>

&#x20;           </button>

&#x20;           <h2 class="text-sm font-bold text-gold uppercase tracking-wider mb-1 flex items-center gap-2">

&#x20;               <i class="fa-solid fa-image"></i> เปลี่ยนรูปโปรไฟล์

&#x20;           </h2>

&#x20;           <p id="avatarTargetName" class="text-xs text-gray-400 mb-4 truncate"></p>

&#x20;           

&#x20;           <form onsubmit="handleAvatarSubmit(event)" class="space-y-3">

&#x20;               <input type="hidden" id="avatarMemberId">

&#x20;               <div>

&#x20;                   <label class="block text-xs font-semibold text-gray-300 mb-1">วาง URL ลิงก์รูปภาพของคุณ:</label>

&#x20;                   <input type="url" id="selfAvatarUrl" required placeholder="https://..." class="w-full bg-black/60 border border-zinc-700 rounded-lg px-3 py-2 text-xs text-white focus:outline-none focus:border-gold">

&#x20;               </div>



&#x20;               <div class="flex items-center gap-3 py-1">

&#x20;                   <span class="text-xs text-gray-400">ตัวอย่าง:</span>

&#x20;                   <div class="w-10 h-10 rounded-full bg-black border border-gold/50 p-0.5 overflow-hidden flex-shrink-0">

&#x20;                       <img id="selfAvatarPreview" src="" alt="Preview" class="w-full h-full object-cover rounded-full">

&#x20;                   </div>

&#x20;               </div>



&#x20;               <div class="pt-2 flex justify-end gap-2 border-t border-zinc-800">

&#x20;                   <button type="button" onclick="closeAvatarModal()" class="px-3.5 py-1.5 rounded-lg text-xs font-bold text-gray-400 bg-zinc-800 hover:bg-zinc-700 transition">ยกเลิก</button>

&#x20;                   <button type="submit" class="px-4 py-1.5 rounded-lg text-xs font-bold text-black bg-gold hover:bg-yellow-400 transition">บันทึกรูปภาพ</button>

&#x20;               </div>

&#x20;           </form>

&#x20;       </div>

&#x20;   </div>



&#x20;   <!-- Modal Form (Founder Edit) -->

&#x20;   <div id="memberModal" class="fixed inset-0 bg-black/85 backdrop-blur-md z-50 flex items-center justify-center p-4 hidden">

&#x20;       <div class="bg-zinc-900 border border-zinc-700 rounded-2xl w-full max-w-md p-5 shadow-2xl relative">

&#x20;           <button onclick="closeMemberModal()" class="absolute top-4 right-4 text-gray-400 hover:text-white text-base">

&#x20;               <i class="fa-solid fa-xmark"></i>

&#x20;           </button>

&#x20;           <h2 id="modalTitle" class="text-base font-bold text-gold uppercase tracking-wider mb-4 flex items-center gap-2">

&#x20;               <i class="fa-solid fa-user-pen"></i> แก้ไขข้อมูลสมาชิก

&#x20;           </h2>

&#x20;           <form id="memberForm" onsubmit="handleFormSubmit(event)" class="space-y-3.5">

&#x20;               <input type="hidden" id="editMemberId">



&#x20;               <div>

&#x20;                   <label class="block text-xs font-semibold uppercase text-gray-300 mb-1">ชื่อสมาชิก / Name</label>

&#x20;                   <input type="text" id="memberName" required placeholder="เช่น Shopee winterfat" class="w-full bg-black/60 border border-zinc-700 rounded-lg px-3 py-2 text-xs text-white focus:outline-none focus:border-gold">

&#x20;               </div>



&#x20;               <div>

&#x20;                   <label class="block text-xs font-semibold uppercase text-gray-300 mb-1">ตำแหน่ง / Role</label>

&#x20;                   <select id="memberRole" class="w-full bg-black/60 border border-zinc-700 rounded-lg px-3 py-2 text-xs text-white focus:outline-none focus:border-gold">

&#x20;                       <option value="FOUNDERS">FOUNDERS 👑</option>

&#x20;                       <option value="ADMIN">ADMIN ⭐</option>

&#x20;                       <option value="VIP">VIP 💎</option>

&#x20;                       <option value="MEMBER">MEMBER 👤</option>

&#x20;                   </select>

&#x20;               </div>



&#x20;               <div>

&#x20;                   <label class="block text-xs font-semibold uppercase text-gray-300 mb-1">รูปโปรไฟล์ (Profile Avatar)</label>

&#x20;                   <div class="space-y-2">

&#x20;                       <div class="flex items-center gap-2">

&#x20;                           <label class="cursor-pointer bg-zinc-800 hover:bg-zinc-700 text-gray-200 border border-zinc-700 px-3 py-1.5 rounded-lg text-xs font-semibold flex items-center gap-1.5 w-max">

&#x20;                               <i class="fa-solid fa-upload text-gold"></i>

&#x20;                               <span>เลือกรูปจากเครื่อง...</span>

&#x20;                               <input type="file" id="memberImageFile" accept="image/\*" onchange="handleImageUpload(event)" class="hidden">

&#x20;                           </label>

&#x20;                           <span id="fileNameDisplay" class="text-\[11px] text-gray-400 truncate max-w-\[180px]">ไม่ได้เลือกไฟล์</span>

&#x20;                       </div>

&#x20;                       <div>

&#x20;                           <input type="url" id="memberAvatarUrl" placeholder="หรือวางลิงก์ URL รูปภาพที่นี่..." class="w-full bg-black/60 border border-zinc-700 rounded-lg px-3 py-2 text-xs text-white focus:outline-none focus:border-gold">

&#x20;                       </div>

&#x20;                   </div>

&#x20;               </div>



&#x20;               <div class="flex items-center gap-3 pt-1">

&#x20;                   <span class="text-xs text-gray-400">ตัวอย่างรูป:</span>

&#x20;                   <div class="w-10 h-10 rounded-full bg-black border border-gold/50 p-0.5 overflow-hidden flex-shrink-0">

&#x20;                       <img id="avatarPreviewImg" src="" alt="Preview" class="w-full h-full object-cover rounded-full">

&#x20;                   </div>

&#x20;               </div>



&#x20;               <div class="grid grid-cols-2 gap-2">

&#x20;                   <div>

&#x20;                       <label class="block text-xs font-semibold uppercase text-gray-300 mb-1">โซเชียล / Social</label>

&#x20;                       <select id="memberSocialType" class="w-full bg-black/60 border border-zinc-700 rounded-lg px-3 py-2 text-xs text-white focus:outline-none focus:border-gold">

&#x20;                           <option value="instagram">Instagram (IG)</option>

&#x20;                           <option value="facebook">Facebook</option>

&#x20;                       </select>

&#x20;                   </div>

&#x20;                   <div>

&#x20;                       <label class="block text-xs font-semibold uppercase text-gray-300 mb-1">สถานะออนไลน์</label>

&#x20;                       <select id="memberOnlineStatus" class="w-full bg-black/60 border border-zinc-700 rounded-lg px-3 py-2 text-xs text-white focus:outline-none focus:border-gold">

&#x20;                           <option value="true">Online 🟢</option>

&#x20;                           <option value="false">Offline ⚪</option>

&#x20;                       </select>

&#x20;                   </div>

&#x20;               </div>



&#x20;               <div>

&#x20;                   <label class="block text-xs font-semibold uppercase text-gray-300 mb-1">ลิงก์โปรไฟล์ / Profile URL</label>

&#x20;                   <input type="url" id="memberSocialUrl" required placeholder="https://instagram.com/..." class="w-full bg-black/60 border border-zinc-700 rounded-lg px-3 py-2 text-xs text-white focus:outline-none focus:border-gold">

&#x20;               </div>



&#x20;               <div class="pt-3 flex justify-end gap-2 border-t border-zinc-800">

&#x20;                   <button type="button" onclick="closeMemberModal()" class="px-3.5 py-1.5 rounded-lg text-xs font-bold text-gray-400 bg-zinc-800 hover:bg-zinc-700 transition">ยกเลิก</button>

&#x20;                   <button type="submit" class="px-4 py-1.5 rounded-lg text-xs font-bold text-black bg-gold hover:bg-yellow-400 transition">บันทึกข้อมูล</button>

&#x20;               </div>

&#x20;           </form>

&#x20;       </div>

&#x20;   </div>



&#x20;   <!-- Delete Modal -->

&#x20;   <div id="deleteModal" class="fixed inset-0 bg-black/85 backdrop-blur-md z-50 flex items-center justify-center p-4 hidden">

&#x20;       <div class="bg-zinc-900 border border-red-500/40 rounded-2xl w-full max-w-sm p-5 shadow-2xl relative text-center">

&#x20;           <div class="w-12 h-12 bg-red-500/10 border border-red-500/30 rounded-full flex items-center justify-center mx-auto mb-3 text-red-400 text-xl">

&#x20;               <i class="fa-solid fa-trash-can"></i>

&#x20;           </div>

&#x20;           <h3 class="text-sm font-bold text-white mb-1">ยืนยันการลบสมาชิก?</h3>

&#x20;           <p id="deleteMemberName" class="text-xs text-gray-400 mb-5">คุณกำลังจะลบสมาชิกคนนี้ออกจากระบบ</p>

&#x20;           

&#x20;           <div class="flex justify-center gap-2">

&#x20;               <button onclick="closeDeleteModal()" class="px-4 py-1.5 rounded-lg text-xs font-bold text-gray-300 bg-zinc-800 hover:bg-zinc-700 transition">ยกเลิก</button>

&#x20;               <button id="confirmDeleteBtn" onclick="confirmDeleteMember()" class="px-4 py-1.5 rounded-lg text-xs font-bold text-white bg-red-600 hover:bg-red-500 transition shadow-lg">ลบสมาชิก</button>

&#x20;           </div>

&#x20;       </div>

&#x20;   </div>



&#x20;   <script>

&#x20;       const STORAGE\_KEY = 'WINTERFAT\_MEMBERS\_DISCORD\_V1';

&#x20;       const DEFAULT\_AVATAR = "https://images.unsplash.com/photo-1568901346375-23c9450c58cd?w=500\&auto=format\&fit=crop\&q=60";

&#x20;       

&#x20;       // รหัสผ่านสำหรับการเปิดสิทธิ์ Founder Access

&#x20;       const FOUNDER\_PIN = "Ilovewinterfat";



&#x20;       const initialDefaultMembers = \[

&#x20;           {

&#x20;               id: 101,

&#x20;               name: "Shopee winterfat",

&#x20;               role: "FOUNDERS",

&#x20;               type: "instagram",

&#x20;               socialUrl: "https://instagram.com",

&#x20;               avatarUrl: DEFAULT\_AVATAR,

&#x20;               isOnline: true

&#x20;           },

&#x20;           {

&#x20;               id: 102,

&#x20;               name: "Lazada Winterfat hamlak",

&#x20;               role: "FOUNDERS",

&#x20;               type: "instagram",

&#x20;               socialUrl: "https://instagram.com",

&#x20;               avatarUrl: DEFAULT\_AVATAR,

&#x20;               isOnline: true

&#x20;           }

&#x20;       ];



&#x20;       let membersData = \[];

&#x20;       let currentFilter = 'ALL';

&#x20;       let searchQuery = '';

&#x20;       let pendingDeleteId = null;

&#x20;       let isFounderAccess = false;



&#x20;       function loadMembers() {

&#x20;           const saved = localStorage.getItem(STORAGE\_KEY);

&#x20;           if (saved) {

&#x20;               try {

&#x20;                   membersData = JSON.parse(saved);

&#x20;               } catch(e) {

&#x20;                   membersData = \[...initialDefaultMembers];

&#x20;               }

&#x20;           } else {

&#x20;               membersData = \[...initialDefaultMembers];

&#x20;               saveMembers();

&#x20;           }

&#x20;       }



&#x20;       function saveMembers() {

&#x20;           localStorage.setItem(STORAGE\_KEY, JSON.stringify(membersData));

&#x20;       }



&#x20;       function resetDefaultData() {

&#x20;           if (confirm("ต้องการรีเซ็ตคืนค่าสมาชิกเริ่มต้นใช่หรือไม่?")) {

&#x20;               membersData = \[...initialDefaultMembers];

&#x20;               saveMembers();

&#x20;               renderMembers();

&#x20;           }

&#x20;       }



&#x20;       function toggleFounderAccess(enabled) {

&#x20;           const toggle = document.getElementById('founderToggle');

&#x20;           if (enabled) {

&#x20;               toggle.checked = false;

&#x20;               document.getElementById('founderPasswordInput').value = '';

&#x20;               document.getElementById('passwordError').classList.add('hidden');

&#x20;               document.getElementById('passwordModal').classList.remove('hidden');

&#x20;           } else {

&#x20;               applyFounderAccess(false);

&#x20;           }

&#x20;       }



&#x20;       function verifyFounderPassword(e) {

&#x20;           e.preventDefault();

&#x20;           const inputPin = document.getElementById('founderPasswordInput').value;

&#x20;           if (inputPin === FOUNDER\_PIN) {

&#x20;               document.getElementById('passwordModal').classList.add('hidden');

&#x20;               document.getElementById('founderToggle').checked = true;

&#x20;               applyFounderAccess(true);

&#x20;           } else {

&#x20;               document.getElementById('passwordError').classList.remove('hidden');

&#x20;           }

&#x20;       }



&#x20;       function cancelPasswordModal() {

&#x20;           document.getElementById('passwordModal').classList.add('hidden');

&#x20;           document.getElementById('founderToggle').checked = false;

&#x20;       }



&#x20;       function applyFounderAccess(enabled) {

&#x20;           isFounderAccess = enabled;

&#x20;           const statusText = document.getElementById('founderStatusText');

&#x20;           const addBtn = document.getElementById('addMemberBtn');



&#x20;           if (isFounderAccess) {

&#x20;               statusText.innerText = 'Founder Access Enabled';

&#x20;               statusText.className = 'text-gold font-bold';

&#x20;               addBtn.classList.remove('opacity-50', 'cursor-not-allowed');

&#x20;               addBtn.classList.add('cursor-pointer');

&#x20;           } else {

&#x20;               statusText.innerText = 'Founder View Only';

&#x20;               statusText.className = 'text-gray-400';

&#x20;               addBtn.classList.add('opacity-50', 'cursor-not-allowed');

&#x20;               addBtn.classList.remove('cursor-pointer');

&#x20;           }



&#x20;           renderMembers();

&#x20;       }



&#x20;       function renderMembers() {

&#x20;           const container = document.getElementById('memberList');

&#x20;           const noResults = document.getElementById('noResults');

&#x20;           container.innerHTML = '';



&#x20;           const filtered = membersData.filter(member => {

&#x20;               const matchesRole = currentFilter === 'ALL' || member.role === currentFilter;

&#x20;               const matchesSearch = member.name.toLowerCase().includes(searchQuery.toLowerCase()) || 

&#x20;                                     member.role.toLowerCase().includes(searchQuery.toLowerCase());

&#x20;               return matchesRole \&\& matchesSearch;

&#x20;           });



&#x20;           if (filtered.length === 0) {

&#x20;               noResults.classList.remove('hidden');

&#x20;           } else {

&#x20;               noResults.classList.add('hidden');

&#x20;           }



&#x20;           filtered.forEach(member => {

&#x20;               const card = document.createElement('div');

&#x20;               card.className = 'luxury-card rounded-2xl p-3.5 sm:p-4 flex items-center justify-between gap-3 w-full relative group';



&#x20;               let roleColorClass = "text-brandRed";

&#x20;               let roleIcon = "👑";

&#x20;               if(member.role === 'ADMIN') {

&#x20;                   roleColorClass = "text-gold";

&#x20;                   roleIcon = "⭐";

&#x20;               } else if(member.role === 'VIP') {

&#x20;                   roleColorClass = "text-purple-400";

&#x20;                   roleIcon = "💎";

&#x20;               } else if(member.role === 'MEMBER') {

&#x20;                   roleColorClass = "text-sky-400";

&#x20;                   roleIcon = "👤";

&#x20;               }



&#x20;               let actionButtonHtml = '';

&#x20;               if (member.type === 'instagram') {

&#x20;                   actionButtonHtml = `

&#x20;                       <a href="${member.socialUrl}" target="\_blank" rel="noopener noreferrer" class="ig-btn inline-flex items-center gap-1.5 text-\[10px] sm:text-xs font-extrabold text-white tracking-wider uppercase transition-all w-max px-3 py-0.5 rounded-full">

&#x20;                           <i class="fa-brands fa-instagram text-xs"></i>

&#x20;                           <span>INSTAGRAM</span>

&#x20;                       </a>

&#x20;                   `;

&#x20;               } else {

&#x20;                   actionButtonHtml = `

&#x20;                       <a href="${member.socialUrl}" target="\_blank" rel="noopener noreferrer" class="inline-flex items-center gap-1.5 text-\[10px] sm:text-xs font-extrabold text-blue-400 hover:text-blue-300 tracking-wider uppercase transition-colors w-max">

&#x20;                           <i class="fa-brands fa-facebook-f text-xs"></i>

&#x20;                           <span>FACEBOOK</span>

&#x20;                       </a>

&#x20;                   `;

&#x20;               }



&#x20;               const avatarChangeBtn = `

&#x20;                   <button onclick="openAvatarModal(${member.id})" title="ใส่ลิงก์รูปของตัวเอง" class="mt-1 text-\[10px] text-zinc-400 hover:text-gold flex items-center gap-1 transition-colors">

&#x20;                       <i class="fa-solid fa-camera"></i>

&#x20;                       <span>เปลี่ยนรูปโปรไฟล์</span>

&#x20;                   </button>

&#x20;               `;



&#x20;               const controlsHtml = isFounderAccess ? `

&#x20;                   <div class="flex items-center gap-1.5 flex-shrink-0">

&#x20;                       <button onclick="openEditModal(${member.id})" title="แก้ไขสมาชิก" class="w-8 h-8 rounded-lg bg-zinc-800/90 hover:bg-gold hover:text-black text-gray-300 border border-zinc-700/80 flex items-center justify-center text-xs transition-all shadow-md">

&#x20;                           <i class="fa-solid fa-pen"></i>

&#x20;                       </button>

&#x20;                       <button onclick="openDeleteModal(${member.id})" title="ลบสมาชิก" class="w-8 h-8 rounded-lg bg-zinc-800/90 hover:bg-red-600 hover:text-white text-gray-300 border border-zinc-700/80 flex items-center justify-center text-xs transition-all shadow-md">

&#x20;                           <i class="fa-solid fa-trash-can"></i>

&#x20;                       </button>

&#x20;                   </div>

&#x20;               ` : '';



&#x20;               card.innerHTML = `

&#x20;                   <div class="flex items-center gap-3 sm:gap-4 min-w-0 flex-1">

&#x20;                       <div class="relative flex-shrink-0">

&#x20;                           <div class="w-12 h-12 sm:w-14 sm:h-14 rounded-full bg-black border border-gold/50 flex items-center justify-center p-0.5 shadow-inner overflow-hidden">

&#x20;                               <img src="${member.avatarUrl || DEFAULT\_AVATAR}" alt="${member.name}" class="w-full h-full object-cover rounded-full" onerror="this.src='${DEFAULT\_AVATAR}'">

&#x20;                           </div>

&#x20;                           <span class="absolute bottom-0 right-0 w-3 h-3 ${member.isOnline ? 'bg-emerald-500 shadow-\[0\_0\_8px\_#10b981]' : 'bg-gray-500'} rounded-full border-2 border-black"></span>

&#x20;                       </div>



&#x20;                       <div class="flex flex-col min-w-0 flex-1">

&#x20;                           <div class="flex items-center gap-1 text-\[10px] sm:text-xs font-bold tracking-wider ${roleColorClass} uppercase mb-0.5">

&#x20;                               <span>${roleIcon}</span>

&#x20;                               <span>${member.role}</span>

&#x20;                           </div>



&#x20;                           <h3 class="text-sm sm:text-base font-bold text-white tracking-wide truncate">

&#x20;                               ${member.name}

&#x20;                           </h3>



&#x20;                           <div class="flex items-center gap-3 flex-wrap">

&#x20;                               ${actionButtonHtml}

&#x20;                               ${avatarChangeBtn}

&#x20;                           </div>

&#x20;                       </div>

&#x20;                   </div>



&#x20;                   ${controlsHtml}

&#x20;               `;



&#x20;               container.appendChild(card);

&#x20;           });



&#x20;           updateCounts();

&#x20;       }



&#x20;       function openAvatarModal(id) {

&#x20;           const member = membersData.find(m => m.id === id);

&#x20;           if (!member) return;



&#x20;           document.getElementById('avatarMemberId').value = member.id;

&#x20;           document.getElementById('avatarTargetName').innerText = `สำหรับสมาชิก: ${member.name}`;

&#x20;           document.getElementById('selfAvatarUrl').value = member.avatarUrl || '';

&#x20;           document.getElementById('selfAvatarPreview').src = member.avatarUrl || DEFAULT\_AVATAR;

&#x20;           

&#x20;           document.getElementById('avatarModal').classList.remove('hidden');

&#x20;       }



&#x20;       function closeAvatarModal() {

&#x20;           document.getElementById('avatarModal').classList.add('hidden');

&#x20;       }



&#x20;       document.getElementById('selfAvatarUrl').addEventListener('input', (e) => {

&#x20;           const url = e.target.value.trim();

&#x20;           document.getElementById('selfAvatarPreview').src = url || DEFAULT\_AVATAR;

&#x20;       });



&#x20;       function handleAvatarSubmit(e) {

&#x20;           e.preventDefault();

&#x20;           const id = document.getElementById('avatarMemberId').value;

&#x20;           const newUrl = document.getElementById('selfAvatarUrl').value.trim();



&#x20;           const index = membersData.findIndex(m => m.id == id);

&#x20;           if (index !== -1) {

&#x20;               membersData\[index].avatarUrl = newUrl || DEFAULT\_AVATAR;

&#x20;               saveMembers();

&#x20;               renderMembers();

&#x20;           }

&#x20;           closeAvatarModal();

&#x20;       }



&#x20;       function updateCounts() {

&#x20;           document.getElementById('count-all').innerText = membersData.length;

&#x20;           document.getElementById('count-founders').innerText = membersData.filter(m => m.role === 'FOUNDERS').length;

&#x20;           document.getElementById('count-admin').innerText = membersData.filter(m => m.role === 'ADMIN').length;

&#x20;           document.getElementById('count-vip').innerText = membersData.filter(m => m.role === 'VIP').length;

&#x20;           document.getElementById('count-member').innerText = membersData.filter(m => m.role === 'MEMBER').length;

&#x20;       }



&#x20;       function filterRole(role) {

&#x20;           currentFilter = role;

&#x20;           const buttons = document.querySelectorAll('.filter-btn');

&#x20;           buttons.forEach(btn => {

&#x20;               btn.className = 'filter-btn px-2.5 sm:px-3 py-1 rounded-full text-\[10px] sm:text-\[11px] font-bold tracking-wider uppercase transition-all duration-300 bg-zinc-900/90 text-gray-400 border border-zinc-800 hover:text-white';

&#x20;           });

&#x20;           event.currentTarget.className = 'filter-btn active-filter px-2.5 sm:px-3 py-1 rounded-full text-\[10px] sm:text-\[11px] font-bold tracking-wider uppercase transition-all duration-300 bg-gold text-black border border-gold shadow-\[0\_0\_10px\_rgba(212,175,55,0.4)]';

&#x20;           renderMembers();

&#x20;       }



&#x20;       document.getElementById('searchInput').addEventListener('input', (e) => {

&#x20;           searchQuery = e.target.value;

&#x20;           renderMembers();

&#x20;       });



&#x20;       function openAddModal() {

&#x20;           if (!isFounderAccess) {

&#x20;               alert("ต้องเปิดสิทธิ์ '👑 Founder Access' บริเวณด้านขวาบนก่อนเพื่อจัดการหรือเพิ่มสมาชิกครับ");

&#x20;               return;

&#x20;           }

&#x20;           document.getElementById('modalTitle').innerHTML = '<i class="fa-solid fa-user-plus text-gold"></i> Add New Member';

&#x20;           document.getElementById('editMemberId').value = '';

&#x20;           document.getElementById('memberForm').reset();

&#x20;           document.getElementById('memberRole').value = 'MEMBER';

&#x20;           document.getElementById('memberAvatarUrl').value = '';

&#x20;           document.getElementById('avatarPreviewImg').src = DEFAULT\_AVATAR;

&#x20;           document.getElementById('fileNameDisplay').innerText = 'ไม่ได้เลือกไฟล์';

&#x20;           document.getElementById('memberModal').classList.remove('hidden');

&#x20;       }



&#x20;       function openEditModal(id) {

&#x20;           if (!isFounderAccess) return;

&#x20;           const member = membersData.find(m => m.id === id);

&#x20;           if (!member) return;



&#x20;           document.getElementById('modalTitle').innerHTML = '<i class="fa-solid fa-user-pen text-gold"></i> แก้ไขข้อมูลสมาชิก';

&#x20;           document.getElementById('editMemberId').value = member.id;

&#x20;           document.getElementById('memberName').value = member.name;

&#x20;           document.getElementById('memberRole').value = member.role;

&#x20;           document.getElementById('memberSocialType').value = member.type || 'instagram';

&#x20;           document.getElementById('memberSocialUrl').value = member.socialUrl || '';

&#x20;           document.getElementById('memberOnlineStatus').value = member.isOnline ? 'true' : 'false';

&#x20;           

&#x20;           document.getElementById('memberAvatarUrl').value = member.avatarUrl || '';

&#x20;           document.getElementById('avatarPreviewImg').src = member.avatarUrl || DEFAULT\_AVATAR;

&#x20;           document.getElementById('fileNameDisplay').innerText = 'ใช้รูปเดิม';



&#x20;           document.getElementById('memberModal').classList.remove('hidden');

&#x20;       }



&#x20;       function closeMemberModal() {

&#x20;           document.getElementById('memberModal').classList.add('hidden');

&#x20;       }



&#x20;       document.getElementById('memberAvatarUrl').addEventListener('input', (e) => {

&#x20;           const url = e.target.value.trim();

&#x20;           document.getElementById('avatarPreviewImg').src = url || DEFAULT\_AVATAR;

&#x20;       });



&#x20;       function handleImageUpload(e) {

&#x20;           const file = e.target.files\[0];

&#x20;           if (file) {

&#x20;               document.getElementById('fileNameDisplay').innerText = file.name;

&#x20;               const reader = new FileReader();

&#x20;               reader.onload = function(evt) {

&#x20;                   const dataUrl = evt.target.result;

&#x20;                   document.getElementById('memberAvatarUrl').value = dataUrl;

&#x20;                   document.getElementById('avatarPreviewImg').src = dataUrl;

&#x20;               };

&#x20;               reader.readAsDataURL(file);

&#x20;           }

&#x20;       }



&#x20;       function handleFormSubmit(e) {

&#x20;           e.preventDefault();



&#x20;           const editId = document.getElementById('editMemberId').value;

&#x20;           const name = document.getElementById('memberName').value.trim();

&#x20;           const role = document.getElementById('memberRole').value;

&#x20;           const type = document.getElementById('memberSocialType').value;

&#x20;           const socialUrl = document.getElementById('memberSocialUrl').value.trim();

&#x20;           const avatarUrl = document.getElementById('memberAvatarUrl').value.trim() || DEFAULT\_AVATAR;

&#x20;           const isOnline = document.getElementById('memberOnlineStatus').value === 'true';



&#x20;           if (!name || !socialUrl) return;



&#x20;           if (editId) {

&#x20;               const memberIndex = membersData.findIndex(m => m.id == editId);

&#x20;               if (memberIndex !== -1) {

&#x20;                   membersData\[memberIndex] = {

&#x20;                       ...membersData\[memberIndex],

&#x20;                       name,

&#x20;                       role,

&#x20;                       type,

&#x20;                       socialUrl,

&#x20;                       avatarUrl,

&#x20;                       isOnline

&#x20;                   };

&#x20;               }

&#x20;           } else {

&#x20;               membersData.push({

&#x20;                   id: Date.now(),

&#x20;                   name,

&#x20;                   role,

&#x20;                   type,

&#x20;                   socialUrl,

&#x20;                   avatarUrl,

&#x20;                   isOnline

&#x20;               });

&#x20;           }



&#x20;           saveMembers();

&#x20;           renderMembers();

&#x20;           closeMemberModal();

&#x20;       }



&#x20;       function openDeleteModal(id) {

&#x20;           if (!isFounderAccess) return;

&#x20;           const member = membersData.find(m => m.id === id);

&#x20;           if (!member) return;



&#x20;           pendingDeleteId = id;

&#x20;           document.getElementById('deleteMemberName').innerText = `คุณกำลังจะลบสมาชิก "${member.name}" ออกจากระบบ`;

&#x20;           document.getElementById('deleteModal').classList.remove('hidden');

&#x20;       }



&#x20;       function closeDeleteModal() {

&#x20;           pendingDeleteId = null;

&#x20;           document.getElementById('deleteModal').classList.add('hidden');

&#x20;       }



&#x20;       function confirmDeleteMember() {

&#x20;           if (pendingDeleteId !== null) {

&#x20;               membersData = membersData.filter(m => m.id !== pendingDeleteId);

&#x20;               saveMembers();

&#x20;               renderMembers();

&#x20;           }

&#x20;           closeDeleteModal();

&#x20;       }



&#x20;       const canvas = document.getElementById('particles-canvas');

&#x20;       const ctx = canvas.getContext('2d');



&#x20;       function resizeCanvas() {

&#x20;           canvas.width = window.innerWidth;

&#x20;           canvas.height = window.innerHeight;

&#x20;       }

&#x20;       window.addEventListener('resize', resizeCanvas);

&#x20;       resizeCanvas();



&#x20;       const particles = Array.from({ length: 45 }, () => ({

&#x20;           x: Math.random() \* canvas.width,

&#x20;           y: Math.random() \* canvas.height,

&#x20;           size: Math.random() \* 2 + 0.5,

&#x20;           speedX: (Math.random() - 0.5) \* 0.3,

&#x20;           speedY: (Math.random() - 0.5) \* 0.3,

&#x20;           opacity: Math.random() \* 0.5 + 0.2,

&#x20;           gold: Math.random() > 0.4

&#x20;       }));



&#x20;       function animateParticles() {

&#x20;           ctx.clearRect(0, 0, canvas.width, canvas.height);



&#x20;           particles.forEach(p => {

&#x20;               p.x += p.speedX;

&#x20;               p.y += p.speedY;



&#x20;               if (p.x < 0) p.x = canvas.width;

&#x20;               if (p.x > canvas.width) p.x = 0;

&#x20;               if (p.y < 0) p.y = canvas.height;

&#x20;               if (p.y > canvas.height) p.y = 0;



&#x20;               ctx.beginPath();

&#x20;               ctx.arc(p.x, p.y, p.size, 0, Math.PI \* 2);

&#x20;               ctx.fillStyle = p.gold 

&#x20;                   ? `rgba(212, 175, 55, ${p.opacity})` 

&#x20;                   : `rgba(255, 255, 255, ${p.opacity \* 0.6})`;

&#x20;               ctx.fill();

&#x20;           });



&#x20;           requestAnimationFrame(animateParticles);

&#x20;       }



&#x20;       window.onload = function() {

&#x20;           loadMembers();

&#x20;           renderMembers();

&#x20;           animateParticles();

&#x20;       };

&#x20;   </script>

</body>

</html>

