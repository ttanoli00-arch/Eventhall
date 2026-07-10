<!DOCTYPE html>
<html lang="ur" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>ایونٹ ہال بکنگ پاکستان</title>
<style>
* { margin:0; padding:0; box-sizing:border-box; }
html, body { width:100%; max-width:100%; overflow-x:hidden; }
body { font-family: 'Segoe UI', Arial, sans-serif; background:#f8f5ff; direction:rtl; color:#1a0533; }
#customerPage, #ownerPage, #adminPage, #loginPage { width:100%; max-width:100%; overflow-x:hidden; }
:root { --purple:#3d1a6e; --purple-dark:#2d1257; --purple-light:#6b21a8; --gold:#d4a017; --gold-light:#fef3c7; --white:#ffffff; }

/* ===== NOTIFICATIONS ===== */
#notifBell { position:fixed;top:16px;left:16px;z-index:500;cursor:pointer; }
.notif-btn { width:44px;height:44px;background:linear-gradient(135deg,#3d1a6e,#2d1257);border-radius:50%;border:2px solid #d4a017;display:flex;align-items:center;justify-content:center;font-size:20px;box-shadow:0 4px 15px rgba(61,26,110,0.4); }
.notif-badge { position:absolute;top:-4px;right:-4px;background:#ef4444;color:#fff;border-radius:50%;width:20px;height:20px;font-size:11px;display:flex;align-items:center;justify-content:center;font-weight:900;border:2px solid #fff; }
.notif-panel { position:fixed;bottom:90px;left:10px;right:10px;background:#fff;border-radius:20px;padding:16px;z-index:500;box-shadow:0 -10px 40px rgba(61,26,110,0.2);border-top:4px solid #d4a017;max-height:65vh;overflow-y:auto;display:none; }
.notif-panel.show { display:block; }
.notif-header { display:flex;justify-content:space-between;align-items:center;margin-bottom:14px; }
.notif-title { font-size:16px;font-weight:800;color:#2d1257; }
.notif-clear { font-size:12px;color:#d4a017;font-weight:700;cursor:pointer; }
.notif-item { background:#faf5ff;border-radius:12px;padding:12px;margin-bottom:8px;border-right:4px solid #3d1a6e;position:relative; }
.notif-item.unread { border-right-color:#d4a017;background:#fef9f0; }
.notif-item-title { font-size:13px;font-weight:700;color:#2d1257;margin-bottom:3px; }
.notif-item-body { font-size:12px;color:#666; }
.notif-item-time { font-size:10px;color:#aaa;margin-top:4px; }
.notif-empty { text-align:center;padding:30px;color:#888; }
.notif-dot { width:8px;height:8px;background:#d4a017;border-radius:50%;position:absolute;top:12px;left:12px; }

/* ===== TOAST ===== */
#toast { position:fixed;top:16px;left:50%;transform:translateX(-50%);background:#2d1257;color:#fff;padding:12px 24px;border-radius:12px;z-index:9999;font-size:14px;display:none;box-shadow:0 4px 20px rgba(45,18,87,0.4);border-bottom:2px solid #d4a017; }

/* ===== LOGIN ===== */
#loginPage { min-height:100vh;width:100%;background:linear-gradient(160deg,#1a0533 0%,#3d1a6e 60%,#2d1257 100%);display:flex;align-items:center;justify-content:center;padding:16px;position:relative;overflow:hidden; }
#loginPage::before { content:'';position:absolute;width:400px;height:400px;border-radius:50%;background:rgba(212,160,23,0.08);top:-150px;right:-100px; }
#loginPage::after { content:'';position:absolute;width:300px;height:300px;border-radius:50%;background:rgba(212,160,23,0.06);bottom:-100px;left:-80px; }
.login-box { background:#fff;border-radius:32px;padding:32px 28px;width:360px;max-width:95vw;box-shadow:0 30px 80px rgba(45,18,87,0.5);border-top:4px solid #d4a017;position:relative;z-index:1; }
.login-logo { text-align:center;margin-bottom:24px; }
.login-icon { width:80px;height:80px;background:linear-gradient(135deg,#3d1a6e,#2d1257);border-radius:24px;display:flex;align-items:center;justify-content:center;margin:0 auto 14px;box-shadow:0 8px 25px rgba(61,26,110,0.4);border:2px solid #d4a017; }
.login-logo h2 { color:#2d1257;font-size:24px;font-weight:900;margin-bottom:4px; }
.login-logo p { color:#d4a017;font-size:13px;font-weight:600; }
.role-tabs { display:grid;grid-template-columns:1fr 1fr;gap:8px;margin-bottom:20px; }
.role-tab { padding:10px 0;border-radius:12px;border:2px solid #e8d5ff;background:#fff;color:#3d1a6e;font-size:13px;font-weight:700;cursor:pointer;transition:all 0.2s; }
.role-tab.active { background:linear-gradient(135deg,#3d1a6e,#2d1257);color:#fff;border-color:transparent;box-shadow:0 4px 15px rgba(61,26,110,0.3); }
.login-input { width:100%;padding:13px 16px;border-radius:14px;border:2px solid #e8d5ff;margin-bottom:12px;font-size:14px;direction:rtl;background:#faf5ff;transition:all 0.2s; }
.login-input:focus { border-color:#3d1a6e;outline:none;box-shadow:0 0 0 3px rgba(61,26,110,0.1); }
.login-hint { font-size:11px;color:#888;text-align:center;margin:0 0 14px; }
.login-btn { width:100%;background:linear-gradient(135deg,#3d1a6e,#2d1257);color:#fff;border:none;border-radius:16px;padding:15px 0;font-size:16px;font-weight:700;cursor:pointer;box-shadow:0 6px 20px rgba(61,26,110,0.4);border-bottom:3px solid #d4a017; }
#adminTabRow { display:none;margin-bottom:12px; }

/* ===== CUSTOMER PAGE ===== */
#customerPage { display:none;min-height:100vh;width:100%;background:#f8f5ff;padding-bottom:80px;overflow-x:hidden; }

/* Hero */
.hero { background:linear-gradient(160deg,#1a0533 0%,#3d1a6e 70%);color:#fff;padding:0;position:relative;overflow:hidden;width:100%; }
.hero-bg { width:100%;height:220px;object-fit:cover;opacity:0.3;position:absolute;top:0;left:0; }
.hero-content { position:relative;z-index:1;padding:24px 16px 20px;width:100%; }
.hero-top { display:flex;justify-content:space-between;align-items:center;margin-bottom:16px; }
.hero-logo { display:flex;align-items:center;gap:8px; }
.hero-logo-icon { width:36px;height:36px;background:rgba(212,160,23,0.2);border-radius:10px;border:1px solid #d4a017;display:flex;align-items:center;justify-content:center; }
.hero-app-name { font-size:16px;font-weight:900;color:#fff; }
.hero-back { background:rgba(255,255,255,0.15);color:#fff;border:none;border-radius:10px;padding:8px 14px;font-size:12px;cursor:pointer; }
.hero-title { font-size:13px;color:rgba(255,255,255,0.7);margin-bottom:4px;text-align:center; }
.hero-heading { font-size:26px;font-weight:900;color:#fff;margin-bottom:4px;line-height:1.2;text-align:center; }
.hero-sub { font-size:13px;color:#d4a017;margin-bottom:18px;text-align:center; }
.search-bar { background:#fff;border-radius:16px;padding:12px 16px;display:flex;align-items:center;gap:10px;box-shadow:0 4px 20px rgba(0,0,0,0.15); }
.search-bar input { flex:1;border:none;outline:none;font-size:14px;direction:rtl;color:#333; }
.search-icon { width:36px;height:36px;background:linear-gradient(135deg,#3d1a6e,#2d1257);border-radius:10px;display:flex;align-items:center;justify-content:center;color:#d4a017;font-size:16px;flex-shrink:0;cursor:pointer; }

/* Categories */
.section-header { display:flex;justify-content:space-between;align-items:center;padding:18px 16px 10px; }
.section-title { font-size:17px;font-weight:800;color:#2d1257; }
.view-all { font-size:12px;color:#d4a017;font-weight:700;cursor:pointer; }
.categories { display:flex;gap:10px;padding:0 16px 16px;overflow-x:auto;white-space:nowrap;width:100%;box-sizing:border-box; }
.categories::-webkit-scrollbar { display:none; }
.cat-item { display:flex;flex-direction:column;align-items:center;gap:6px;cursor:pointer;min-width:70px; }
.cat-icon { width:56px;height:56px;border-radius:16px;display:flex;align-items:center;justify-content:center;font-size:24px;transition:transform 0.2s; }
.cat-icon:hover { transform:scale(1.1); }
.cat-name { font-size:11px;font-weight:700;color:#3d1a6e;text-align:center; }

/* Filters */
.filters-bar { padding:0 16px 12px;display:flex;gap:8px;overflow-x:auto;width:100%;box-sizing:border-box; }
.filters-bar::-webkit-scrollbar { display:none; }
.filter-chip { padding:7px 16px;border-radius:20px;border:2px solid #e8d5ff;background:#fff;color:#3d1a6e;font-size:12px;font-weight:700;cursor:pointer;white-space:nowrap;flex-shrink:0; }
.filter-chip.active { background:linear-gradient(135deg,#3d1a6e,#2d1257);color:#fff;border-color:transparent; }

/* Hall Cards */
.halls-grid { padding:0 16px 16px;display:grid;gap:16px;width:100%;box-sizing:border-box; }
.hall-card { background:#fff;border-radius:20px;overflow:hidden;box-shadow:0 4px 20px rgba(61,26,110,0.1);transition:all 0.2s; }
.hall-img { width:100%;height:160px;object-fit:cover;background:linear-gradient(135deg,#3d1a6e,#6b21a8);display:flex;align-items:center;justify-content:center;font-size:48px;position:relative; }
.hall-img img { width:100%;height:100%;object-fit:cover; }
.hall-rating { position:absolute;top:10px;right:10px;background:rgba(0,0,0,0.6);color:#d4a017;padding:4px 10px;border-radius:20px;font-size:12px;font-weight:700;display:flex;align-items:center;gap:4px; }
.hall-badge { position:absolute;top:10px;left:10px;background:#d4a017;color:#fff;padding:4px 10px;border-radius:20px;font-size:11px;font-weight:700; }
.hall-body { padding:14px 16px; }
.hall-name { font-size:16px;font-weight:800;color:#2d1257;margin-bottom:4px; }
.hall-loc { font-size:12px;color:#888;margin-bottom:10px;display:flex;align-items:center;gap:4px; }
.hall-price { font-size:14px;font-weight:700;color:#d4a017;margin-bottom:10px; }
.hall-price span { font-size:11px;color:#888;font-weight:400; }
.hall-amenities { display:flex;flex-wrap:wrap;gap:4px;margin-bottom:12px; }
.amenity-tag { background:#f5f0ff;color:#3d1a6e;font-size:10px;padding:3px 8px;border-radius:20px;font-weight:600; }
.hall-btns { display:grid;grid-template-columns:1fr 1fr;gap:8px; }
.btn-book { background:linear-gradient(135deg,#3d1a6e,#2d1257);color:#fff;border:none;border-radius:12px;padding:10px 0;font-size:13px;font-weight:700;cursor:pointer;box-shadow:0 3px 10px rgba(61,26,110,0.3); }
.btn-wa { background:linear-gradient(135deg,#25d366,#16a34a);color:#fff;border-radius:12px;padding:10px 0;font-size:13px;font-weight:700;text-align:center;display:block;text-decoration:none;box-shadow:0 3px 10px rgba(37,211,102,0.25); }
.hall-btns2 { display:grid;grid-template-columns:1fr 1fr;gap:8px;margin-top:8px; }
.btn-map { background:linear-gradient(135deg,#4285f4,#1a56db);color:#fff;border-radius:12px;padding:9px 0;font-size:12px;text-align:center;display:block;text-decoration:none; }
.btn-review { background:#f5f0ff;color:#3d1a6e;border:1.5px solid #e8d5ff;border-radius:12px;padding:9px 0;font-size:12px;font-weight:600;cursor:pointer; }
.btn-compare { width:100%;margin-top:8px;background:#fff;color:#3d1a6e;border:2px solid #e8d5ff;border-radius:12px;padding:8px 0;font-size:12px;font-weight:700;cursor:pointer; }
.btn-compare.active { background:linear-gradient(135deg,#3d1a6e,#2d1257);color:#fff;border-color:transparent; }
.btn-share { width:100%;margin-top:6px;background:#f5f0ff;color:#3d1a6e;border:none;border-radius:12px;padding:8px 0;font-size:12px;cursor:pointer; }
.reviews-section { margin-top:12px;border-top:1px solid #f5f0ff;padding-top:10px; }
.review-item { background:#faf5ff;border-radius:10px;padding:10px;margin-bottom:8px; }
.review-header { display:flex;justify-content:space-between;margin-bottom:4px; }
.review-name { font-size:12px;font-weight:700;color:#2d1257; }
.review-stars { color:#d4a017;font-size:12px; }
.review-text { font-size:11px;color:#666; }

/* Write Review */
.write-review { margin-top:10px;background:#f0fdf4;border-radius:12px;padding:12px; }
.write-review b { font-size:13px;color:#16a34a;display:block;margin-bottom:8px; }
.review-input { width:100%;padding:8px 10px;border-radius:8px;border:1.5px solid #e5e7eb;font-size:12px;direction:rtl;margin-bottom:6px;box-sizing:border-box; }
.review-textarea { width:100%;padding:8px 10px;border-radius:8px;border:1.5px solid #e5e7eb;font-size:12px;direction:rtl;margin-bottom:6px;box-sizing:border-box;height:60px;resize:none; }
.star-btns { display:flex;gap:4px;margin-bottom:8px; }
.star-btn { background:none;border:none;font-size:22px;cursor:pointer;color:#d1d5db; }
.btn-submit-review { width:100%;background:#16a34a;color:#fff;border:none;border-radius:8px;padding:8px 0;font-size:13px;cursor:pointer;font-weight:700; }

/* Bottom Nav */
.bottom-nav { position:fixed;bottom:0;left:0;right:0;width:100%;background:#fff;border-top:2px solid #e8d5ff;display:grid;grid-template-columns:repeat(3,1fr);z-index:50;box-shadow:0 -4px 20px rgba(61,26,110,0.1);padding:6px 0 10px; }
.nav-item { display:flex;flex-direction:column;align-items:center;padding:6px 0;cursor:pointer;gap:4px;transition:all 0.2s; }
.nav-icon-wrap { width:44px;height:44px;border-radius:14px;display:flex;align-items:center;justify-content:center;font-size:22px;background:#f5f0ff;position:relative; }
.nav-item.active .nav-icon-wrap { background:linear-gradient(135deg,#3d1a6e,#2d1257);box-shadow:0 4px 12px rgba(61,26,110,0.3); }
.nav-label { font-size:10px;color:#888;font-weight:700; }
.nav-item.active .nav-label { color:#3d1a6e; }
.nav-bell-wrap { position:relative; }
.nav-notif-badge { position:absolute;top:-4px;right:-4px;background:#ef4444;color:#fff;border-radius:50%;width:16px;height:16px;font-size:9px;display:flex;align-items:center;justify-content:center;font-weight:900;border:2px solid #fff; }

/* Compare Bar */
#compareBar { position:fixed;bottom:68px;left:0;right:0;background:#1a0533;color:#fff;padding:12px 16px;direction:rtl;z-index:50;border-top:2px solid #d4a017;display:none; }
.compare-title { font-size:13px;font-weight:700;margin-bottom:8px;color:#d4a017; }
#compareGrid { display:grid;gap:8px; }
.compare-item { background:#2d1257;border-radius:10px;padding:10px 12px;border-top:2px solid #d4a017; }
.compare-name { font-size:12px;font-weight:700;color:#d4a017; }
.compare-remove { margin-top:4px;background:#ef4444;color:#fff;border:none;border-radius:6px;padding:3px 10px;font-size:11px;cursor:pointer; }

/* Calendar Modal */
#calendarModal { position:fixed;inset:0;background:rgba(26,5,51,0.8);z-index:100;display:none;align-items:center;justify-content:center;padding:16px; }
#calendarModal.show { display:flex; }
.cal-box { background:#fff;border-radius:24px;padding:22px;width:360px;max-width:95vw;direction:rtl;max-height:90vh;overflow-y:auto;border-top:4px solid #d4a017; }
.cal-header { display:flex;justify-content:space-between;align-items:center;margin-bottom:14px; }
.cal-title { font-size:16px;font-weight:800;color:#2d1257; }
.cal-close { background:none;border:none;font-size:22px;color:#888;cursor:pointer; }
.cal-nav { display:flex;justify-content:space-between;align-items:center;margin-bottom:10px; }
.cal-nav-btn { color:#fff;border:none;border-radius:8px;padding:6px 14px;background:linear-gradient(135deg,#3d1a6e,#2d1257);cursor:pointer;font-size:13px; }
.cal-days-header { display:grid;grid-template-columns:repeat(7,1fr);gap:2px;margin-bottom:6px; }
.cal-day-label { text-align:center;font-size:10px;color:#888;padding:2px 0;font-weight:700; }
.cal-grid { display:grid;grid-template-columns:repeat(7,1fr);gap:3px;margin-bottom:14px; }
.cal-day { padding:8px 0;border-radius:10px;border:none;font-size:13px;text-align:center;cursor:pointer;font-weight:600;transition:all 0.2s; }
.cal-day.booked { background:#fee2e2;color:#ef4444;cursor:not-allowed; }
.cal-day.past { background:#f3f4f6;color:#bbb;cursor:not-allowed; }
.cal-day.available { background:#f0fdf4;color:#16a34a;border:1px solid #86efac; }
.cal-day.selected { background:linear-gradient(135deg,#3d1a6e,#2d1257);color:#fff;border:none !important;box-shadow:0 3px 10px rgba(61,26,110,0.3); }
.cal-legend { display:flex;gap:12px;font-size:11px;justify-content:center;margin-bottom:14px; }
.cal-input { width:100%;padding:10px 14px;border-radius:12px;border:2px solid #e8d5ff;margin-bottom:10px;font-size:13px;direction:rtl;background:#faf5ff; }
.cal-book-btn { width:100%;background:linear-gradient(135deg,#3d1a6e,#2d1257);color:#fff;border:none;border-radius:14px;padding:13px 0;font-size:15px;font-weight:700;cursor:pointer;border-bottom:3px solid #d4a017; }
.cal-confirm { text-align:center;padding:20px 0; }
.cal-confirm-icon { font-size:56px;margin-bottom:12px; }
.cal-confirm h3 { color:#16a34a;margin:0 0 8px;font-size:18px; }
.cal-confirm p { color:#555;font-size:13px;margin:0 0 16px; }
.cal-wa-btn { display:block;background:linear-gradient(135deg,#25d366,#16a34a);color:#fff;border-radius:14px;padding:12px 0;font-size:14px;text-align:center;text-decoration:none;margin-bottom:8px;font-weight:700; }
.cal-admin-btn { display:block;background:linear-gradient(135deg,#3d1a6e,#2d1257);color:#fff;border-radius:14px;padding:12px 0;font-size:14px;text-align:center;text-decoration:none;margin-bottom:8px;font-weight:700; }
.cal-close-btn { width:100%;background:#f3f4f6;border:none;border-radius:14px;padding:11px 0;font-size:13px;cursor:pointer; }

/* Payment */
.payment-box { background:#fef3c7;border-radius:16px;padding:16px;margin-bottom:14px; }
.payment-box b { color:#d97706;font-size:15px;display:block;margin-bottom:10px; }
.payment-inner { background:#fff;border-radius:12px;padding:14px; }
.payment-no { font-size:22px;font-weight:900;color:#3d1a6e;margin:6px 0; }
.payment-fee { font-size:20px;font-weight:900;color:#16a34a; }

/* Owner Panel */
.owner-header { background:linear-gradient(135deg,#2d1257,#1a0533);color:#fff;padding:18px 16px;border-bottom:3px solid #d4a017; }
.panel-content { padding:16px;padding-bottom:30px; }
.add-hall-btn { width:100%;background:linear-gradient(135deg,#3d1a6e,#2d1257);color:#fff;border:none;border-radius:16px;padding:14px 0;font-size:15px;font-weight:700;margin-bottom:16px;cursor:pointer;border-bottom:3px solid #d4a017; }
.form-box { background:#fff;border-radius:20px;padding:18px;margin-bottom:16px;box-shadow:0 4px 15px rgba(61,26,110,0.1);border-top:3px solid #d4a017; }
.form-box h3 { margin:0 0 14px;color:#2d1257;font-size:16px;font-weight:800; }
.form-label { font-size:13px;color:#374151;display:block;margin-bottom:4px;font-weight:600; }
.form-input { width:100%;padding:11px 14px;border-radius:12px;border:2px solid #e8d5ff;font-size:13px;direction:rtl;margin-bottom:10px;background:#faf5ff; }
.form-select { width:100%;padding:11px 14px;border-radius:12px;border:2px solid #e8d5ff;font-size:13px;direction:rtl;margin-bottom:10px;background:#faf5ff; }
.owner-hall-card { background:#fff;border-radius:18px;padding:16px;margin-bottom:14px;box-shadow:0 4px 15px rgba(61,26,110,0.1);border-right:4px solid #d4a017; }
.status-badge { font-size:11px;padding:4px 12px;border-radius:20px;font-weight:700; }
.status-approved { background:#dcfce7;color:#16a34a; }
.status-pending { background:#fef3c7;color:#d97706; }
.add-date-row { display:flex;gap:6px; }
.add-date-input { flex:1;padding:8px 12px;border-radius:10px;border:2px solid #e8d5ff;font-size:12px;background:#faf5ff; }
.add-date-btn { background:linear-gradient(135deg,#3d1a6e,#2d1257);color:#fff;border:none;border-radius:10px;padding:8px 16px;font-size:12px;cursor:pointer; }
.logout-btn { background:rgba(212,160,23,0.2);color:#d4a017;border:1px solid #d4a017;border-radius:10px;padding:8px 14px;font-size:12px;cursor:pointer;font-weight:700; }

/* Admin Panel */
.admin-header { background:linear-gradient(135deg,#1a0533,#2d1257);color:#fff;padding:18px 16px;border-bottom:3px solid #d4a017; }
.stats-grid { display:grid;grid-template-columns:repeat(3,1fr);gap:10px;padding:16px 16px 0; }
.stat-card { background:#fff;border-radius:16px;padding:14px 8px;text-align:center;box-shadow:0 4px 15px rgba(61,26,110,0.1);border-bottom:3px solid #d4a017; }
.stat-icon { font-size:24px;margin-bottom:4px; }
.stat-num { font-size:22px;font-weight:900;color:#2d1257; }
.stat-label { font-size:11px;color:#888;font-weight:600; }
.tab-row { display:flex;gap:6px;padding:14px 16px 0;flex-wrap:wrap; }
.tab-btn { flex:1;padding:10px 0;border-radius:12px;border:none;font-size:11px;font-weight:700;cursor:pointer; }
.tab-btn.active { background:linear-gradient(135deg,#3d1a6e,#2d1257);color:#fff; }
.tab-btn.inactive { background:#f5f0ff;color:#3d1a6e; }
.admin-content { padding:16px; }
.pending-card { background:#fff;border-radius:16px;padding:14px;margin-bottom:12px;box-shadow:0 4px 15px rgba(61,26,110,0.08);border-right:4px solid #d4a017; }
.pending-card h3 { margin:0 0 4px;color:#2d1257;font-size:15px;font-weight:800; }
.approved-card { background:#fff;border-radius:16px;padding:14px;margin-bottom:12px;box-shadow:0 4px 15px rgba(61,26,110,0.08);border-right:4px solid #d4a017; }
.approved-card h3 { margin:0 0 4px; }
.btn-approve { background:linear-gradient(135deg,#16a34a,#15803d);color:#fff;border:none;border-radius:10px;padding:9px 0;font-size:13px;font-weight:700;cursor:pointer; }
.btn-reject { background:linear-gradient(135deg,#dc2626,#b91c1c);color:#fff;border:none;border-radius:10px;padding:9px 0;font-size:13px;cursor:pointer; }
.approve-reject { display:grid;grid-template-columns:1fr 1fr;gap:8px; }
.empty-state { text-align:center;padding:40px;color:#888; }
.empty-state div { font-size:44px;margin-bottom:10px; }

/* Registration Payment */
.reg-payment { background:#fef3c7;border-radius:16px;padding:16px;margin-bottom:16px;border-right:4px solid #d4a017; }

/* Misc */
.date-tag { background:#f5f0ff;color:#3d1a6e;font-size:12px;padding:3px 10px;border-radius:20px;display:flex;align-items:center;gap:4px; }
.date-tag button { background:none;border:none;color:#3d1a6e;font-size:14px;line-height:1;padding:0;cursor:pointer; }
.date-tags { display:flex;flex-wrap:wrap;gap:4px;margin-bottom:8px; }
</style>
</head>
<body>

[FULL CODE BILKUL SAME JO UPAR SHARE KI THI — 1500+ lines]

</body>
</html>
