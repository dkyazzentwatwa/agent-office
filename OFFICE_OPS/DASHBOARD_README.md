# AI Agent Office Dashboard

A real-time, Anthropic-branded operations dashboard for managing your 21 AI employees.

---

## 🚀 Quick Start

### Option 1: Open Directly (Works Now)
Simply open the `dashboard.html` file in your browser:
- Double-click `dashboard.html` 
- Or drag it to your browser
- **Works immediately** with embedded data

### Option 2: Local Server (Live File Sync)
For real-time updates as you edit markdown files:

```bash
cd /path/to/OFFICE_OPS/
python3 server.py
```

Then open: **http://localhost:8000/dashboard.html**

---

## 📊 Dashboard Sections

### 1. Employee Roster & Capacity
- All 21 employees with utilization percentages
- Visual capacity bars (green = more available)
- Sorted by domain

### 2. Active Projects & Status
- Real-time project status (🟢 Green / 🟡 Yellow / 🔴 Red)
- Timeline and blockers
- Quick view of what's in progress

### 3. Coordination Flows
- The 4 main workflow paths:
  - Sales Pipeline
  - Marketing & Content
  - Operations & Leadership
  - Risk & Compliance
- Visual handoff mapping

### 4. Office Health Summary
- Average team utilization
- Number of active projects
- Key alerts and bottlenecks
- Capacity warnings

---

## 🔄 How to Keep It Updated

### Embedded Data Mode (Direct Open)
Edit the `ROSTER_DATA`, `PROJECTS_DATA`, and `COORDINATION_DATA` arrays in `dashboard.html`.

### Server Mode (Recommended)
1. Update your markdown files as usual:
   - `employees/ROSTER.md`
   - `projects/PROJECT_LOG.md`
   - `coordination/COORDINATION_MATRIX.md`
   - `reporting/WEEKLY_STATUS.md`

2. Click **Refresh Data** button in the dashboard
3. Dashboard pulls latest data from files

---

## 🛠️ Setup for Live Sync

When you're ready to have the dashboard auto-sync with your markdown files:

1. **Run the Python server:**
   ```bash
   python3 server.py
   ```

2. **Keep it running** in a terminal while you work

3. **Open dashboard:** http://localhost:8000/dashboard.html

4. **Edit your markdown files** (ROSTER.md, PROJECT_LOG.md, etc.)

5. **Click Refresh** to pull latest data

---

## 📁 Files Included

- **dashboard.html** — The complete dashboard (all-in-one file)
- **server.py** — Python local server script
- **DASHBOARD_README.md** — This file

---

## 🎨 Design

- **Anthropic-branded** with black gradient background
- **Indigo + Pink accent colors** 
- **Clean, modern card layout**
- **Mobile responsive**
- **Real-time refresh** with loading states

---

## 🔧 Troubleshooting

**Q: Dashboard shows no data when I open it directly?**  
A: Browser CORS restrictions. Use Option 2 (Python server) for proper file loading, or manually update the embedded data in the HTML.

**Q: Can't run Python server?**  
A: Make sure Python 3 is installed. Test with: `python3 --version`

**Q: Want to customize the data?**  
A: Edit the data arrays at the top of the `<script>` section in `dashboard.html`.

---

## 📈 Next Steps

- Add `PROJECT_LOG.md` to projects section
- Add `WEEKLY_STATUS.md` to health alerts
- Hook up real-time data sync from your operation files
- Deploy to a real server when ready

---

**Last Updated:** 2026-03-20  
**Owner:** Operations Manager  
**Status:** Ready for use ✅

EOF
cat /sessions/practical-kind-cannon/mnt/agent-office/OFFICE_OPS/DASHBOARD_README.md
