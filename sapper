
# I use Tabs
from random import randint as rnt


class Cell:
	def __init__(self):
		self.around_mines = 0
		self.mine = False
		self.fl_open = False

	def add_around_mine(self):
		self.around_mines += 1

	def set_mine(self):
		self.mine = True

	def to_open(self):
		self.fl_open = True


class GameField:
	def __init__(self, n, m):
		self.game_field = self.creat_game_field(n)
		self.mines_lst = self.creat_mines_lst(n, m)
		self.set_mines(n)

	def init(self, n, m):
		self.__init__(n, m)

	@staticmethod
	def creat_game_field(n):
		game_field = []
		for i in range(n):
			temp_lst = []
			for j in range(n):
				temp_lst.append(Cell())
			game_field.append(temp_lst)
		return game_field

	@staticmethod
	def creat_mines_lst(n, m):
		mines_lst = []
		count_mines = 0
		while count_mines < m:
			mine = (rnt(0, n - 1), rnt(0, n - 1))
			if mine not in mines_lst:
				mines_lst.append(mine)
				count_mines += 1
		return mines_lst

	def set_mines(self, n):
		for coords in self.mines_lst:
			x, y = coords
			out_range = (-1, n)
			for i in range(x - 1, x + 2):
				if i in out_range:
					continue
				for j in range(y - 1, y + 2):
					if j in out_range:
						continue
					self.game_field[i][j].add_around_mine()
			self.game_field[x][y].set_mine()
		return

	def show(self):
		for row in self.game_field:
			for cell in row:
				if cell.mine:
					print('*', end=' ')
				else:
					print(cell.around_mines, end=' ')
			print()


z = GameField(5, 5)
z.show()
