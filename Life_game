class Game_standarts:
  def __init__(self , list):
    self.cells = list

  def check_neighbours(self, pos: list , system=[[-1 , -1] , [-1 , 0] , [-1 , 1] , [0 , -1] , [0 , 1] , [1 , -1] , [1 , 0] , [1 , 1]]):
    count = 0
    for i in system:
        if self.cells[(pos[0] + i[0]) % len(self.cells)][(pos[1] + i[1]) % len(self.cells[0])]:
            count += 1
    return count

  def change_generation(self , check_neighbours):
    cells2 =[[]]
    for i in range(len(self.cells)):
      for j in range(len(self.cells[0])):
        cells2[i][j]=0
    for i in range(len(self.cells)):
      for j in range(len(self.cells[0])):
        if self.cells[i][j]:
          if (check_neighbours([i , j]) < 2) or (check_neighbours([i , j]) > 3):
            cells2[i][j] = 0
          else:
            cells2[i][j] = 1
        else:
          if check_neighbours([i , j]) == 3:
            cells2[i][j] = 1
          else:
            cells2[i][j] = 0
    self.cells = cells2
    return self.cells

  def print_field(self):
    for i in range(len(self.cells)):
      for j in range(len(self.cells[0])):
        print(self.cells[i][j], end=' ')
      print()
    return 0

  def play_game(self,check_neighbours,change_generation,print_field):
    print_field(self.cells)
    previous_cells = self.cells
    while (previous_cells != change_generation(self.cells)):
      new_cells = change_generation(self.cells)
      print_field(new_cells)
      previous_cells = new_cells
    return 0
    
if __name__ == "__main__":
  b =[[1,0,0],[0,0,0],[0,0,0]]
  a = Game_standarts(b)
  a.play_game
