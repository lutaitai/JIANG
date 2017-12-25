# JIANG
Test for git
#dan xiancheng
from time import ctime,sleep
import threading

def talk(content,loop):
    for i in range(loop):
        print("start talk %s %s"%(content,ctime()))
        sleep(2)
def write(content,loop):
    for i in range(loop):
        print("start write %s %s"%(content,ctime()))
        sleep(3)

threads=[]
t1=threading.Thread(target=talk,args=('Speak:hello,51zxw',2))
threads.append(t1)
t2=threading.Thread(target=talk,args=('Write:life is short you need python!',2))
threads.append(t2)

if __name__=='__main__':
    for t in threads:
        t.start()
    for t in threads:
        t.join()
    print("all thread end! %r" %ctime())
