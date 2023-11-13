### Prep commit trước khi merge
- Nếu không có merge branch commit -> Squash tất cả commit cho đến trước commit cần squash
- Nếu có merge commit
	- Soft Reset tất cả commit cho đến trước commit cần squash
	- Sau đó commit lại toàn bộ change trong 1 commit
	- Sau đó push origin branch_name --force, không push trực tiếp

## Làm việc với các repo có image
- Commit code
- Lên Gitlab, vào mục pipeline, nhấn chạy build image
- Lên k9s tìm image, đợi update và test