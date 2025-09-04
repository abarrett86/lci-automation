web: bash -lc 'set -euo pipefail
echo "--- starting qgtunnel ---"
./.qgtunnel/bin/qgtunnel ./qgtunnel.yml &
QG_PID=$!
sleep 2
echo "--- listening sockets ---"
( command -v ss && ss -lnt ) || netstat -lnt
echo "--- qgtunnel ps ---"
ps -ef | grep qgtunnel | grep -v grep || true
echo "--- starting n8n ---"
N8N_HOST=0.0.0.0 N8N_PORT=$PORT n8n start'