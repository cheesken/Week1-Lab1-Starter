# CMPE 273 – Week 1 Lab 1: Your First Distributed System (Starter)
- `python-http/` (Flask + requests)

## Lab Goal
Build **two services** that communicate over the network:
- **Service A** (port 8080): `/health`, `/echo?msg=...`
- **Service B** (port 8081): `/health`, `/call-echo?msg=...` calls Service A

## Testing
### When both services are running
(venv) monster@Ananyas-MacBook-Pro cmpe273-week1-lab1-starter % curl "http://127.0.0.1:8081/call-echo?msg=hello"
{"service_a":{"echo":"hello"},"service_b":"ok"}
### When service-a isn't running
(venv) monster@Ananyas-MacBook-Pro cmpe273-week1-lab1-starter % curl "http://127.0.0.1:8081/call-echo?msg=hello"
{"error":"HTTPConnectionPool(host='127.0.0.1', port=8080): Max retries exceeded with url: /echo?msg=hello (Caused by NewConnectionError(\"HTTPConnection(host='127.0.0.1', port=8080): Failed to establish a new connection: [Errno 61] Connection refused\"))","service_a":"unavailable","service_b":"ok"}
