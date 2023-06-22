# Find-wifi-password
import subprocess data = subprocess.check_output(['netsh', 'wlan', 'show', 'profiles'], shell=True).decode('utf-8').split('\n')  profiles = [i.split(":")[1][1:-1] for i in data if "All User Profile" in i]   for i in profiles:     results = subprocess.check_output(['netsh', 'wlan', 'show', 'profile', i, 'key=clear']).decode('utf-8').split('\n')
