push:
	git add . && git commit -m "$(m)" && git push

# Dùng: make push m="fix bug"
import subprocess, sys
new
msg = " ".join(sys.argv[1:]) or "update"
for cmd in [["git", "add", "."], ["git", "commit", "-m", msg], ["git", "push"]]:
    subprocess.run(cmd, check=True)
