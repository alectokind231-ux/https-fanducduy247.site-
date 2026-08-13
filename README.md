
# đức duy vào đây 😈😈😈😈😈😈😈😈😈
cheat fan ducduy đù má anh tense gaming giúp em đi mà cái file hack của anh em bị lỗi giúp đi
anh tense gaming ơi em bị cái lỗi giúp đi  
 using System;
using System.Drawing;
using System.Windows.Forms;

namespace AimPanelDemo
{
    public class MainForm : Form
    {
        private Panel sidebar;
        private Panel content;
        private TrackBar trkDelay, trkFov;
        private TextBox txtDelay, txtFov;
        private Button btnAim, btnMouse, btnRadius, btnLock, btnKnocked;

        // === KÍCH THƯỚC CHÍNH XÁC NHƯ ẢNH ===
        const int RỘNG_SIDEBAR = 50;    // ✅ Menu bên trái rất hẹp như ảnh
        const int LỀ_TRONG = 12;
        const int RỘNG_SO = 55;
        const int CAO_NUT = 24;

        public MainForm()
        {
            CreateWindow();
            CreateSidebar();
            CreateContent();
            ShowDemoAim();
        }

        private void CreateWindow()
        {
            Text = "Demo";
            Width = 520;   // ✅ Vừa vặn như ảnh
            Height = 320;
            StartPosition = FormStartPosition.CenterScreen;
            FormBorderStyle = FormBorderStyle.FixedSingle;
            MaximizeBox = false;
            BackColor = Color.FromArgb(30, 30, 35);
        }

        private void CreateSidebar()
        {
            sidebar = new Panel
            {
                Dock = DockStyle.Left,
                Width = RỘNG_SIDEBAR,
                BackColor = Color.FromArgb(35, 35, 40)
            };
            Controls.Add(sidebar);

            // Nút biểu tượng góc trên
            Label icon = new Label
            {
                Text = "⚡",
                ForeColor = Color.FromArgb(255, 60, 100),
                Font = new Font("Segoe UI", 16, FontStyle.Bold),
                Location = new Point(10, 10),
                AutoSize = true
            };
            sidebar.Controls.Add(icon);

            // Biểu tượng cài đặt dưới
            Label gear = new Label
            {
                Text = "⚙",
                ForeColor = Color.Gray,
                Font = new Font("Segoe UI", 12),
                Location = new Point(13, Height - 45),
                AutoSize = true
            };
            sidebar.Controls.Add(gear);
        }

        private void CreateContent()
        {
            content = new Panel
            {
                Dock = DockStyle.Fill,
                BackColor = Color.FromArgb(25, 25, 30)
            };
            Controls.Add(content);
        }

        // ==================================================
        // ✅ BỐ CỤC Y HỆT ẢNH — DEMO
        // ==================================================
        private void ShowDemoAim()
        {
            content.Controls.Clear();
            int X = LỀ_TRONG;
            int X_SO = content.Width - LỀ_TRONG - RỘNG_SO;
            int Y = 10;

            // === CỘT TRÁI: AIMBOT ===
            Label lblAimBot = new Label
            {
                Text = "Aimbot",
                ForeColor = Color.White,
                Font = new Font("Segoe UI", 11, FontStyle.Bold),
                Location = new Point(X, Y),
                AutoSize = true
            };
            btnAim = TaoNutOnOff(X_SO, Y, true); // ✅ Mặc định BẬT như ảnh
btnAim.Click += (s, e) => {
    bool dangBat = (bool)btnAim.Tag;
    dangBat = !dangBat;
    btnAim.Tag = dangBat;
    btnAim.Text = dangBat ? "ON" : "OFF";
    btnAim.BackColor = dangBat ? Color.FromArgb(220, 40, 80) : Color.FromArgb(50, 50, 60);

    if (dangBat == true)
    {
        MessageBox.Show("✅ Aimbot ĐÃ BẬT! Đang tìm đầu địch...");
    }
    else
    {
        MessageBox.Show("❌ Aimbot ĐÃ TẮT!");
    }
};
            // Delay Aimbot
            Label lblDelay = new Label
            {
                Text = "Delay Aimbot",
                ForeColor = Color.FromArgb(160, 160, 165),
                Font = new Font("Segoe UI", 9),
                Location = new Point(X, Y + 40),
                AutoSize = true
            };
            trkDelay = new TrackBar
            {
                Minimum = 0, Maximum = 500, Value = 229,
                Location = new Point(X, Y + 60),
                Size = new Size(X_SO - X - 8, 30)
            };
            txtDelay = new TextBox
            {
                Text = "229ms", Size = new Size(RỘNG_SO, CAO_NUT),
                Location = new Point(X_SO, Y + 60),
                BackColor = Color.FromArgb(40, 40, 50), ForeColor = Color.White,
                BorderStyle = BorderStyle.None, Font = new Font("Segoe UI", 9), TextAlign = HorizontalAlignment.Center
            };
            trkDelay.Scroll += (s, e) => txtDelay.Text = trkDelay.Value + "ms";
            txtDelay.TextChanged += (s, e) => {
                string val = txtDelay.Text.Replace("ms", "").Trim();
                if (int.TryParse(val, out int v) && v >= 0 && v <= 500) trkDelay.Value = v;
            };

            // === CỘT PHẢI: AIM SETTINGS ===
            int X2 = 240;
            int X2_SO = content.Width - LỀ_TRONG - RỘNG_SO;

            Label lblSettings = new Label
            {
                Text = "Aim Settings",
                ForeColor = Color.White,
                Font = new Font("Segoe UI", 11, FontStyle.Bold),
                Location = new Point(X2, Y),
                AutoSize = true
            };

            // Aim Mouse
            Label lblMouse = new Label
            {
                Text = "Aim Mouse",
                ForeColor = Color.FromArgb(160, 160, 165),
                Font = new Font("Segoe UI", 9),
                Location = new Point(X2, Y + 35),
                AutoSize = true
            };
            btnMouse = TaoNutOnOff(X2_SO, Y + 30, false);

            // FOV
            Label lblFov = new Label
            {
                Text = "FOV",
                ForeColor = Color.FromArgb(160, 160, 165),
                Font = new Font("Segoe UI", 9),
                Location = new Point(X2, Y + 65),
                AutoSize = true
            };
            trkFov = new TrackBar
            {
                Minimum = 10, Maximum = 360, Value = 124,
                Location = new Point(X2, Y + 85),
                Size = new Size(X2_SO - X2 - 8, 30)
            };
            txtFov = new TextBox
            {
                Text = "124.20px", Size = new Size(RỘNG_SO, CAO_NUT),
                Location = new Point(X2_SO, Y + 85),
                BackColor = Color.FromArgb(40, 40, 50), ForeColor = Color.White,
                BorderStyle = BorderStyle.None, Font = new Font("Segoe UI", 9), TextAlign = HorizontalAlignment.Center
            };
            trkFov.Scroll += (s, e) => txtFov.Text = trkFov.Value + ".20px";

            // Show FOV Radius
            Label lblRadius = new Label
            {
                Text = "Show FOV Radius",
                ForeColor = Color.FromArgb(160, 160, 165),
                Font = new Font("Segoe UI", 9),
                Location = new Point(X2, Y + 115),
                AutoSize = true
            };
            btnRadius = TaoNutOnOff(X2_SO, Y + 110, true);

            // Lock Head
            Label lblLock = new Label
            {
                Text = "Lock Head",
                ForeColor = Color.FromArgb(160, 160, 165),
                Font = new Font("Segoe UI", 9),
                Location = new Point(X2, Y + 145),
                AutoSize = true
            };
            btnLock = TaoNutOnOff(X2_SO, Y + 140, false);

            // Ignore Knocked
            Label lblKnocked = new Label
            {
                Text = "Ignore Knocked",
                ForeColor = Color.FromArgb(160, 160, 165),
                Font = new Font("Segoe UI", 9),
                Location = new Point(X2, Y + 175),
                AutoSize = true
            };
            btnKnocked = TaoNutOnOff(X2_SO, Y + 170, true);

            content.Controls.AddRange(new Control[] {
                lblAimBot, btnAim, lblDelay, trkDelay, txtDelay,
                lblSettings, lblMouse, btnMouse, lblFov, trkFov, txtFov,
                lblRadius, btnRadius, lblLock, btnLock, lblKnocked, btnKnocked
            });
        }

        // === NÚT ON/OFF MÀU ĐỎ NHƯ ẢNH ===
        private Button TaoNutOnOff(int x, int y, bool bat)
        {
            Button btn = new Button
            {
                Text = bat ? "ON" : "OFF",
                Size = new Size(RỘNG_SO, CAO_NUT),
                Location = new Point(x, y),
                BackColor = bat ? Color.FromArgb(220, 40, 80) : Color.FromArgb(50, 50, 60),
                ForeColor = Color.White,
                Font = new Font("Segoe UI", 8, FontStyle.Bold),
                FlatStyle = FlatStyle.Flat,
                FlatAppearance = { BorderSize = 0 },
                Tag = bat
            };
            btn.Click += (s, e) => {
                bool hienTai = (bool)btn.Tag;
                hienTai = !hienTai;
                btn.Tag = hienTai;
                btn.Text = hienTai ? "ON" : "OFF";
                btn.BackColor = hienTai ? Color.FromArgb(220, 40, 80) : Color.FromArgb(50, 50, 60);
            };
            return btn;
        }
    }
}
