
from pathlib import Path

source = Path("/mnt/data/README_GitHub_Profile.md")
content = source.read_text(encoding="utf-8")
content = content.replace("YOUR_GITHUB_USERNAME", "PhamThanh03")
content = content.replace(
    "> Hãy thay các đường dẫn `PhamThanh03/REPOSITORY_NAME` bằng repository thật của bạn. Chỉ giữ những dự án đã được đẩy lên GitHub.",
    "> Cập nhật tên repository bên dưới khi các dự án đã được tạo và đẩy lên GitHub."
)
content = content.replace(
    "<!-- Khi có repository, bạn có thể thay bảng trên bằng liên kết trực tiếp:\n- [Phone Warranty Management](https://github.com/PhamThanh03/phone-warranty-management)\n- [Network Labs](https://github.com/PhamThanh03/network-labs)\n- [Personal Web Projects](https://github.com/PhamThanh03/web-byme)\n-->",
    """<!-- Sau khi tạo các repository với đúng tên bên dưới, có thể bỏ comment và dùng các liên kết này:
- [Phone Warranty Management](https://github.com/PhamThanh03/phone-warranty-management)
- [Network Labs](https://github.com/PhamThanh03/network-labs)
- [Personal Web Projects](https://github.com/PhamThanh03/web-byme)
-->"""
)
content = content.replace("`YOUR_EMAIL@example.com`", "`Thay bằng email bạn muốn công khai`")
output = Path("/mnt/data/README_PhamThanh03.md")
output.write_text(content, encoding="utf-8")
print(f"Đã tạo file cá nhân hóa: {output}\nDung lượng: {output.stat().st_size} bytes")
