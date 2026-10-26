# Ảnh redesign — 26/10/2026

143 ảnh cuối đã được chủ app duyệt: 129 ảnh còn thiếu, 1 nền MeterParcel sửa sang cyan,
3 ảnh store đã duyệt trước và 10 ảnh pack Levain. Danh sách đường dẫn, kích thước,
dung lượng và SHA256 đầy đủ ở [manifest.json](manifest.json).

| App | Số ảnh | Vị trí |
|---|---:|---|
| Paperboat | 75 (38 A + 37 B) | [Paperboat](Paperboat/) |
| Passby | 31 B | [Passby](Passby/) |
| Patchgraph | 23 B | [Patchgraph](Patchgraph/) |
| MeterParcel | 2 B (nền sửa + scene đã duyệt) | [MeterParcel](MeterParcel/) |
| MotifSplice | 1 B đã duyệt | [MotifSplice](MotifSplice/) |
| NegativeIndex | 1 B đã duyệt | [NegativeIndex](NegativeIndex/) |
| Levain | 10 ảnh pack | [levain](../../levain/) |

A giữ đường dẫn tương đối trong app; B giữ đường dẫn tương đối trong `store-art/<App>/`.
Các file A/B ở bộ này là bản bàn giao để tải về và nối vào dự án theo handoff.
Ảnh chụp màn hình và clip thật tiếp tục thuộc luồng capture sau build.

10 ảnh Levain được xuất bằng builder hiện có và thêm vào [manifest pack](../../levain/manifest.json),
giữ nguyên 33 entry cũ, thành 43 entry; app kiểm SHA256 từng file khi tải.
