import psutil

# Define thresholds
CPU_THRESHOLD = 80
MEMORY_THRESHOLD = 80
DISK_THRESHOLD = 80

# Check CPU usage
cpu_usage = psutil.cpu_percent()
if cpu_usage > CPU_THRESHOLD:
    print(f"CPU Usage is high: {cpu_usage}%")

# Check memory usage
memory_usage = psutil.virtual_memory().percent
if memory_usage > MEMORY_THRESHOLD:
    print(f"Memory Usage is high: {memory_usage}%")

# Check disk usage
disk_usage = psutil.disk_usage('/').percent
if disk_usage > DISK_THRESHOLD:
    print(f"Disk Usage is high: {disk_usage}%")

# Check running processes
for proc in psutil.process_iter():
    if proc.cpu_percent() > CPU_THRESHOLD or proc.memory_percent() > MEMORY_THRESHOLD:
        print(f"High CPU/Memory Process: {proc.name()}")
