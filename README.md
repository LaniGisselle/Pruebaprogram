
import sys
from PyQt5.QtCore import Qt
from PyQt5.QtWidgets import QApplication, QMainWindow, QPushButton, QWidget, QLabel, QHBoxLayout, QVBoxLayout

from Caja import Caja

class Caja(QLabel):
    def __init__(self, color):
        super().__init__()
        self.setStyleSheet(f'background-color: {color}')


class Ventana(QMainWindow):
    def __init__(self) -> None:
        super().__init__()

        caja1 = Caja('plum')
        caja2 = Caja('aquamarine')
        caja3 = Caja('gray')
        caja4 = Caja('olive')
        caja5 = Caja('navy')
        caja6 = Caja('green')

        LayoutHorizontal1 = QHBoxLayout()
        LayoutVertical1 = QVBoxLayout()
        LayoutHorizontal2 = QHBoxLayout()

        LayoutHorizontal1.addWidget(caja1)
        LayoutHorizontal1.addLayout(LayoutVertical1)


        LayoutVertical1.addWidget(caja2)
        LayoutVertical1.addWidget(caja3)
        LayoutVertical1.addLayout(LayoutHorizontal2)

        LayoutHorizontal2.addWidget(caja4)
        LayoutHorizontal2.addWidget(caja5)
        LayoutHorizontal2.addWidget(caja6)
    

        widget = QWidget()
        widget.setLayout(LayoutHorizontal1)

        self.setCentralWidget(widget)


if __name__ == '__main__':
    app = QApplication(sys.argv)
    window = Ventana()
    window.show();
    sys.exit(app.exec())
