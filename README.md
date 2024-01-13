# Dijkstra
1.Inicializace vzdáleností:

  distances = {vertex: float('infinity') for vertex in graph}: Vytváří slovník distances, kde klíčem je každý vrchol grafu a hodnotou je nekonečno. Tento slovník bude sloužit k uchování nejkratších dosud známých    vzdáleností od počátečního vrcholu.

  distances[start] = 0: Nastavuje vzdálenost počátečního vrcholu na 0, protože vzdálenost od sebe samého je nula.
  
2.Inicializace fronty s prioritou:

  priority_queue = [(0, start)]: Vytváří frontu s prioritou, kde každý prvek je dvojice (vzdálenost, vrchol). Počáteční vrchol je umístěn do fronty s vzdáleností 0.

3.Hlavní část Dijkstrova algoritmu:

  while priority_queue:: Pokud fronta s prioritou není prázdná, algoritmus pokračuje.

  current_distance, current_vertex = heapq.heappop(priority_queue): Z fronty se odeberu informace o vrcholu s nejnižší aktuální vzdáleností.

  Procházíme sousední vrcholy aktuálního vrcholu:

  for neighbor, weight in graph[current_vertex].items():
  distance = current_distance + weight: Spočítáme vzdálenost od počátečního vrcholu k sousednímu vrcholu přes aktuální vrchol.

  if distance < distances[neighbor]:: Pokud nově spočítaná vzdálenost je menší než dosud známá vzdálenost k sousednímu vrcholu, aktualizujeme vzdálenost.

  heapq.heappush(priority_queue, (distance, neighbor)): Přidáme sousední vrchol do fronty s nově vypočítanou vzdáleností.
