import numpy as np
import matplotlib.pyplot as plt
from matplotlib.animation import FuncAnimation

# البيانات الأساسية
سنوات = np.arange(1, 6)  # 5 سنوات
أرباح = [7680, 8880, 10560, 11760, 13440]  # الأرباح السنوية
عقارات = [1, 2, 3]  # عدد العقارات المملوكة
قيمة_العقارات = [200000, 400000, 600000]  # قيمة العقارات المملوكة

# إنشاء الشكل والرسومات
fig, (ax1, ax2) = plt.subplots(2, 1, figsize=(10, 8))
fig.suptitle('خطة التملك العقاري عبر شركة BV', fontsize=16)

# الرسم البياني الأول: الأرباح السنوية
خط_أرباح, = ax1.plot([], [], marker='o', color='blue', label='الأرباح السنوية')
ax1.set_xlim(0, 6)
ax1.set_ylim(0, 15000)
ax1.set_xlabel('السنة')
ax1.set_ylabel('الأرباح (يورو)')
ax1.set_title('الأرباح السنوية على مدار 5 سنوات')
ax1.grid(True)
ax1.legend()

# الرسم البياني الثاني: قيمة العقارات
خط_عقارات, = ax2.plot([], [], marker='o', color='green', label='قيمة العقارات')
ax2.set_xlim(0, 6)
ax2.set_ylim(0, 700000)
ax2.set_xlabel('السنة')
ax2.set_ylabel('قيمة العقارات (يورو)')
ax2.set_title('قيمة العقارات المملوكة')
ax2.grid(True)
ax2.legend()

# دالة التحديث للرسوم المتحركة
def update(frame):
    # تحديث بيانات الأرباح
    خط_أرباح.set_data(sنوات[:frame], أرباح[:frame])
    
    # تحديث بيانات العقارات
    if frame >= 1:
        خط_عقارات.set_data([1, 2, 3][:frame-1], قيمة_العقارات[:frame-1])
    
    return خط_أرباح, خط_عقارات

# إنشاء الرسوم المتحركة
ani = FuncAnimation(fig, update, frames=6, interval=1000, blit=True)

# حفظ الفيديو
ani.save('شركة_BV_خطة_التملك_العقاري.mp4', writer='ffmpeg')

plt.show()
