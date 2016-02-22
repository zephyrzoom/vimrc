#!/usr/bin/env python3
#author = 707

import urllib.request
import json
import time
import threading

CHAT_INFO_URL = 'http://www.panda.tv/ajax_chatinfo?roomid='

def scanRooms():
    for x in range(1,100):
        getChatInfo(x)
        threading.Thread(target=getChatInfo, args=([x]))

def getChatInfo(roomid):
    with urllib.request.urlopen(CHAT_INFO_URL + str(roomid)) as f:
        data = f.read().decode('utf-8')
    chatInfo = json.loads(data)
    chatAddr = chatInfo['data']['chat_addr_list'][0]
    socketIP = chatAddr.split(':')[0]
    socketPort = int(chatAddr.split(':')[1])
    print(socketIP, socketPort)

def writeDanmu():
    pass

def main():
    scanRooms()

if __name__ == '__main__':
    main()