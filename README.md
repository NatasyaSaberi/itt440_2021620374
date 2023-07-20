# itt440_2021620374
skill based test 

import socket

def send_and_receive_data(host, port, data):
    try:
        # Create a TCP socket
        with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as client_socket:
            # Connect to the server
            client_socket.connect((host, port))

            # Send data
            client_socket.sendall(data.encode())

            # Receive and read server response
            response = client_socket.recv(1024)
            print("Server response:", response.decode())

    except ConnectionRefusedError:
        print("Connection refused. Make sure the server is running and the address is correct.")
    except Exception as e:
        print("Error:", e)

if __name__ == "__main__":
    host = "izani.synology.me"
    port = 8443
    student_id = '2021620374' 

    send_and_receive_data(host, port, student_id)


