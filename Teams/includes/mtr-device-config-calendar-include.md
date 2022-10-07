
Para ajudar os usuários a agendar reuniões com mais facilidade em uma Sala do Teams, você pode criar listas de salas e locais Exchange Online. 

As listas de salas do Exchange e os Locais do Outlook são usados para controlar quais contas de recursos (e, portanto, as Salas do Teams às quais estão associadas) aparecem no Localizador de Salas do Outlook. O Localizador de Salas é um recurso do Outlook que ajuda os usuários a encontrar salas próximas a elas, disponíveis para reserva e atender a outros critérios, como a disponibilidade de uma exibição.

As listas de salas são um tipo especial de grupo de distribuição do Exchange que permite agrupar contas de recursos (e, portanto, as Salas do Teams às quais elas estão associadas) de maneira significativa. Por exemplo, talvez você queira criar listas de salas para todas as salas em cada prédio do campus.

Os Locais do Outlook permitem definir atributos específicos sobre uma conta de recurso e sua Sala do Teams. Alguns dos atributos que você pode definir são:

- Edifício
- Cidade
- Capacidade
- Se o local é acessível para cadeira de rodas
- Nomes de áudio, vídeo e exibição

Usando uma combinação de listas de salas e atributos de local selecionados por um usuário, o Localizador de Salas no Outlook mostrará uma lista de salas disponíveis para reserva. Para fazer o melhor uso de listas de salas e locais, crie listas de salas com base em um atributo de local, como a construção. Por exemplo, defina os atributos de cidade e local de construção para cada conta de recurso e, em seguida, adicione cada conta de recurso a uma lista de sala de construção. Quando um usuário tenta escolher uma sala para reservar, o Outlook mostrará uma lista de cidades e as listas de salas disponíveis em cada uma dessas cidades.

> [!IMPORTANT]
> Cada conta de recurso precisa ter seus atributos de local definidos. Se esses atributos, especialmente cidade, construção e capacidade, não estiverem definidos, essas salas não aparecerão como opções disponíveis para reserva, mesmo que uma lista de salas os contenha.

Para criar uma lista de salas, siga as instruções em [Criar uma lista de salas](/exchange/recipients/room-mailboxes?view=exchserver-2019&preserve-view=true#create-a-room-list).

Para configurar os atributos de local para uma conta de recurso, consulte [Set-Place](/powershell/module/exchange/set-place).
