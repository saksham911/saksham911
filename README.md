from pyfiglet import Figlet
os. system("clear")
pyf = Figlet (font= 'puffy')
a = pyf. renderText ("Video Chat App without Multi-Threading")
b = pyf .renderText ("Server")
N
os. system ("tput setaf 3")
print(a)
import socket, cv?, pickle, struct
# Socket Create
server_socket = socket. socket (socket .AF_INET, socket.SOCK_STREAM)
host _name = socket .gethostname ()
host_ip = socket. gethostbyname (host _name)
print('HOST IP:', host_ip)
port = 9999
socket_address = (host_ip,port)
# Socket Bind
server_socket.bind(socket_address)
# Socket Listen
server_socket. listen (1)
print ("Listening at:", socket _address)
# Socket Accept
while True:
client_socket, addr = server_socket.accept ()
print ('Connected to:' ‚addr)
if client_socket:
vid = cv2. VideoCapture(0)
while (vid. isOpened()):
ret, image = vid. read()
img_serialize = pickle.dumps (image)
message = struct.pack("", Len (img_serialize))+img_serialize
client_socket.sendall (message)
cv2. imshow ('Video from Server', image)
key = cv2. waitKey (10)
if key ==13:
client_socket.close()
