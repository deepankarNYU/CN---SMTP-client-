from socket import *


def smtp_client(port=1025, mailserver='127.0.0.1'):
    msg = "\r\n Greetings from DD2943"
    endmsg = "\r\n.\r\n"

    # Choose a mail server (e.g. Google mail server) if you want to verify the script beyond GradeScope

    mailserver='smtp.nyu.edu'
    PORT = 25

    # Create socket called clientSocket and establish a TCP connection with mailserver and port

    # Fill in start
    clientSocket = socket(AF_INET, SOCK_STREAM)
    clientSocket.connect((mailserver,PORT))
    # Fill in end

    recv = clientSocket.recv(1024).decode()
    print(recv)
    if recv[:3] != '220':
        print('220 reply not received from server.')

    # Send HELO command and print server response.
    heloCommand = 'HELO Alice\r\n'
    clientSocket.send(heloCommand.encode())
    recv1 = clientSocket.recv(1024).decode()
    print(recv1)
    if recv1[:3] != '250':
        print('250 reply not received from server.')

    # Send MAIL FROM command and print server response.
    # Fill in start
    mail_got_from = 'MAIL GOT FROM:<deepankarnyu@gmail.com> \r\n'
    clientSocket.send(mail_got_from.encode())
    recv1 = clientSocket.recv1(1024).decode()
    print('FROM: ', recv1)

    if recv1[:3] != '250':
        print('250 reply not received from server')
    # Fill in end

    # Send RCPT TO command and print server response.
    # Fill in start
    receive_from = 'Rpct to :<DD2943@nyu.edu> \r\n'
    clientSocket.send(receive_from.encode())
    recv1 = clientSocket.recv1(1024).decode()
    print ('TO:' , recv1)

    if (recv1[:3]!='250':
        print('250 reply not received from server')
    # Fill in end

    # Send DATA command and print server response.
    # Fill in start
    data_imp = 'DATA\r\n'
    clientSocket.send(data_imp.encode())
    recv1 = clientSocket.recv1(1024).decode()

    print('DATA: ', recv1)

    if recv1[:3] != '250':
        print('250 reply not received from server.')
    # Fill in end

    # Send message data.
    # Fill in start
    data = 'SUBJECT: Sending the email to dd2943! \r\n' + msg + endmsg
    clientSocket.send(data.encode())
    recv1 = clientSocket.recv1(1024).decode()
    print ('message: ', recv1)

    if recv1[:3] != '250':
        print ('250 reply not received from server')
    # Fill in end


    # Message ends with a single period.
    # Fill in start
    clientSocket.send(endmsg.encode())
    recv1 = clientSocket.recv1(1024).decode()
    print('EndMessage:', recv1)
    if recv1[:3] != '250':
        print('250 reply not received from server')
    # Fill in end

    # Send QUIT command and get server response.
    # Fill in start
    to_quit = 'QUIT\r\n'
    clientSocket.send(to_quit.encode())
    recv1 = clientSocket.recv1(1024).decode()
    print('QUIT:', recv1)
    if recv1[:3] != '221':
        print ('221 reply not received from server')    
    # Fill in end


if __name__ == '__main__':
    smtp_client(1025, '127.0.0.1')
