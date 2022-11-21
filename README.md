import datetime
import time
import json
import threading


def function_1():
    with open('new.json') as json_file:
        data = json.load(json_file)
        for it in data.values():
            time.sleep(1)
            print(it)


# thread_list = []
# for i in range(1):
#     x = threading.Thread(target=function_1)
#     thread_list.append(x)
#     x.start()
#
# for thread in thread_list:
#     thread.join()
#
# b = (datetime.datetime.today() - starting_time).seconds
# print(f"it took {b} seconds")



starting_time = datetime.datetime.today()

print(starting_time)

for i in range(1):
    x = threading.Thread(target=function_1)
    x.start()

b = (datetime.datetime.today() - starting_time).seconds
print(f"it took {b} seconds")
