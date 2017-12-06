---
title: "Configurar um atendedor automático de sistema telefônico"
ms.author: tonysmit
author: tonysmit
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c

description: "Learn how to set up and test Phone System (Cloud PBX) auto attendents for efficient call handling for your organization. "
---

# Configurar um atendedor automático de sistema telefônico

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o [aviso de isenção de responsabilidade](6fc2687c-0abf-43b8-aa54-7c3b2a84b67c.md#MT_Footer). Para sua referência, veja a versão em inglês deste artigo [aqui](https://support.office.com/en-us/article/6fc2687c-0abf-43b8-aa54-7c3b2a84b67c). 
  
Os atendedores automáticos são muito úteis e permitem que as pessoas que ligam para sua organização naveguem pelo sistema de menus para direcioná-los aos departamentos, fila de chamadas, uma pessoa ou o operador certo. Você pode criar um atendedor automático para sua organização usando o centro de administração do Skype for Business. Para criar um novo atendedor automático, vá para **Encaminhamento de chamada** na navegação esquerda e depois selecione **Atendedores automáticos** > **Adicionar novo**.
  
Se você quiser saber mais sobre os atendedores automáticos, consulte [Quais são os atendedores automáticos do sistema telefônico?](what-are-phone-system-auto-attendants.md).
  
## Etapa 1 - Introdução

- Antes de você poder criar e configurar atendedores automáticos, é necessário obter ou transferir seus números de serviço de chamada gratuita ou tarifada. Depois de obter números de serviço de chamada gratuita ou tarifada, eles serão exibidos no ** Centro de administração do Skype for Business** > **Voz** > na guia **Números de telefone** e o **Tipo de número** será listado como **Serviço - Chamada Gratuita**. Para obter seus números de serviço, consulte [Obtendo números telefônicos de serviço do Skype for Business](getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md) ou se você desejar transferir um número de serviço existente, consulte[Transferir números de telefone para o Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md). **Os números (assinante)** do usuário não podem ser atribuídos a atendedores automáticos. Se você estiver fora dos EUA, não será possível usar o Centro de administração do Skype for Business para obter números de serviço. Vá[Gerenciar números de telefone para sua organização](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) para ver como fazer isso fora dos EUA.
    
    > [!CAUTION]
    > Para obter e usar os números de telefone de chamada gratuita, você precisa configurar a comunicação créditos. Para fazer este consulte [O que são créditos de comunicações?](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md) e[Configurar comunicações créditos para sua organização](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md). 
  
- Sua organização deve ter (no mínimo) uma licença Enterprise E3 plus **Sistema telefônico** ou uma licença Enterprise E5. O número de licenças de usuário do **Sistema telefônico** atribuídos impactos o número de serviço números que está disponível para ser usado para os atendedores automáticos. Os números de atendedores automáticos que depende as números **Sistema telefônico** e **Conferência de áudio** licenças atribuídas em sua organização. Para saber mais sobre licenciamento,[Skype para Business e Teams Microsoft complemento licenciamento](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
    > [!TIP]
    > Para redirecionar chamadas para um operador ou uma opção de menu que é um usuário com uma licença de **Sistema telefônico** Online, você precisará habilitá-las para o Enterprise Voice ou atribua chamando planos no Office 365 a eles. Consulte[Atribuir Skype para Business e Teams Microsoft licenças](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Você também pode usar o Windows PowerShell. Executar por exemplo:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
## Etapa 2 - Criar um novo atendedor automático

No **Centro de administração do Skype for Business**, clique em **Encaminhamento de chamadas** > **Atendedores Automáticos** e clique em **Adicionar novas**:
  
### Editar página de informações gerais

Na página Editar informações gerais, insira ou escolha:
  
![New auto attendant page 1.](../images/edacec94-9384-4a87-be0a-5c49a151287e.png)
  
|||
|:-----|:-----|
|**1** <br/> |**Nome** Insira um nome de exibição descritivo para o atendedor automático. O nome é obrigatório e pode conter até 64 caracteres, incluindo espaços. Ele será listado na coluna **Nome** da guia **Atendedores automáticos**.  <br/> |
|**2** <br/> |**Número de telefone** Selecione um número de telefone para o atendedor automático. Um número de telefone é obrigatório e você poderá escolher qualquer número de serviço de chamada tarifada e gratuita disponível que você tenha para sua organização. Se não existirem números de telefone listados, você deverá obter um número de serviço de chamada tarifada e gratuita. Vá[Obtendo números telefônicos de serviço do Skype for Business](getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md) para obtê-lo. <br/> > [!NOTE]> Os números do **usuário (assinante)** não podem ser atribuídos aos atendedores automáticos.          |
|**3** <br/> |**Fuso horário** Você deve definir o fuso horário para o atendedor automático, mas ele não precisa corresponder ao fuso horário do endereço principal de sua organização. Cada atendedor automático pode ter um fuso horário diferente e os horários comerciais definidos para o atendedor automático serão definidos com base no fuso horário que você selecionar aqui. <br/> |
|**4** <br/> |**Idioma** Selecione o idioma que você deseja usar para o atendedor automático entre os idiomas disponíveis listados. O idioma definido aqui é aquele que o atendedor automático usará para interagir com as pessoas que ligarem para ele, e todos os prompts do sistema serão reproduzidos nesse idioma. <br/> |
|**5** <br/> |**Reconhecimento de fala** O reconhecimento de fala está disponível e se esta opção for marcada, as pessoas que ligam podem usar a entrada de voz no idioma definido. Você pode desabilitar o reconhecimento de fala desmarcando-a se desejar permitir apenas que as pessoas usem o teclado do telefone. <br/> |
|**6** <br/> |**Operador** Isso é opcional e não precisa ser definido para o atendedor automático. No entanto, você pode definir a opção **Operador** para as pessoas que ligam conseguirem sair dos menus para falar com uma pessoa que possa ajudá-las. <br/>  A tecla 0 é atribuída automaticamente ao Operador. <br/>  Se você configurá-lo, você também deverá falar para as pessoas que ligarem que esta é uma opção disponível nas **Editar opções de menu** na página **Administração de chamadas no horário comercial**. Se você definir um operador em seu atendedor automático, deverá inserir o texto do prompt correspondente na caixa **Os chamadores ouvirão** ou alterar o arquivo de áudio para incluir esta opção. Por exemplo, "Para falar com o operador, pressione 0". <br/>  Você pode definir um dos seguintes como Operador: <br/>  Uma **pessoa em sua empresa** que seja um usuário Online com uma licença de **Sistema telefônico** que está habilitada para Enterprise Voice ou atribuído chamando planos no Office 365. <br/> > [!NOTE]>  Não há suporte para os usuários hospedados localmente que usam o Skype for Business Server 2015 ou o Lync Server 2013 e o 2010.           Uma **fila de chamadas** que você configurou. <br/>  Você pode configurá-lo para que a pessoa que liga seja enviada para a caixa postal. Para isso, selecione **Pessoa em sua empresa** e defina as chamadas dessa pessoa para serem encaminhadas diretamente para a caixa postal. <br/> |
   
### Página Selecionar as horas de operação

Por padrão, os horários comerciais são definidos como 24 por dia, 7 dias por semana; portanto, todos os horários são considerados horários comerciais. Todos os horários que não estão incluídos nos horários comerciais são considerados horários fora do expediente. Se você selecionar a opção **Personalizar** e definir os horários comerciais, então a nova página chamada **Administração de chamadas após o expediente** será adicionada e você terá que configurar a administração de chamadas para horário fora do experiente para o atendedor automático.
  
![New auto attendant Hours of operation.](../images/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)
  
|||
|:-----|:-----|
|**1** <br/> |Selecione a opção **Personalizar** para selecionar horários comerciais específicos no calendário. Quando você selecionar **Personalizar**, os horários comerciais serão definidos de segunda a sexta, das 900h às 17h, por padrão.  <br/> |
|**2** <br/> |Para alterar os horários comerciais, destaque os horários comerciais que deseja definir usando o calendário. O calendário permite que você selecione os horários comerciais em intervalo de 30 minutos e os horários comerciais que você selecionar aqui serão baseados no fuso horário que você definir na página **Informações gerais**. Para configurar um intervalo (horário de almoço, por exemplo), desmarque ou arraste para desmarcar o horário no calendário. Você também pode ter vários intervalos que podem ser definidos dentro dos horários comerciais.  <br/> |
   
### Página Administração de chamadas em horários comerciais

> [!TIP]
> Se você usar um cronograma personalizado de horários comerciais, também deverá configurar a administração de chamadas para horários fora do expediente. Uma página **Administração de chamadas após o expediente** será adicionada, portanto, você pode configurar essas opções e você terá as mesmas opções que as de **Administração de chamadas de horários comerciais**. 
  
Você pode configurar as saudações, os prompts e os menus para as pessoas que ligarem para o número de telefone do atendedor automático de sua organização ouvirem durante os horários comerciais.
  
![Business hours call handling.](../images/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
  
|||
|:-----|:-----|
|**1**|**Saudação da empresa** A saudação de horários comerciais é opcional e pode ser definida como **Nenhuma**. Neste caso, o chamador não ouvirá mensagem ou saudação antes de a chamada ser administrada por uma das opções que você selecionar. Você também pode carregar um arquivo de áudio (nos formatos .wav, mp3 ou .wma) ou criar uma saudação personalizada usando a conversão de texto em fala. **Nenhuma** Nenhuma saudação será reproduzida quando as pessoas ligarem para número do atendedor automático. **Criar saudação personalizada** Se você escolher isso, deverá inserir o texto que deseja que o sistema leia (até 1000 caracteres). Por exemplo, você inseriria "Bem-vindo à Contoso. Sua ligação é importante para nós." na caixa de texto **Os chamadores ouvirão**. **Carregar um arquivo de áudio** Se você escolher isso, deverá gravar a saudação e depois carregar o arquivo de áudio (nos formatos .wav, .mp3 ou .wma).|
|**2**| Você pode selecionar o que ocorre com as chamadas que chegam durante o horário comercial. Você pode escolher uma das seguintes opções: **Desconectar** Se você selecioná-la, a pessoa que ligar será desconectada depois de ouvir uma saudação do horário comercial. **Redirecionar chamada** Isso pode ser usado para enviar a chamada automaticamente para: **Pessoa em sua empresa** que seja um usuário Online com uma licença de **Sistema telefônico** que está habilitada para Enterprise Voice ou atribuído chamando planos no Office 365. Você pode configurá-lo para a pessoa que estiver ligando possa ser enviada para a caixa postal. Para fazer isso, selecione uma **pessoa na sua empresa** e essa pessoa terá suas chamadas serem encaminhadas diretamente para a caixa postal.> [!NOTE]>  Não há suporte para os usuários hospedados localmente que usam o Skype for Business Server 2015 ou o Lync Server 2013 e o 2010.           Uma **Fila de chamadas** o uso de uma fila de chamadas permite que a chamada seja transferidas para uma fila de chamadas existente que você configurou Outro **Atendedor automático** Você pode usar um atendedor automático existente para criar um segundo nível de opções de menu contendo um submenu. Eles são chamados de atendedores automáticos aninhados. **Executar prompt do menu opções** Essa opção também pode ser usada par permitir que você configure um prompt que deseje reproduzir.|
|**3**|**Prompt do menu** Para criar o prompt do menu principal, você pode usar a conversão de texto em fala ou carregar um arquivo de áudio (.wav, .mp3 ou .wma). Você pode digitar o prompt na caixa **Os chamadores ouvirão** ou gravar um arquivo de áudio e dizer, por exemplo: "Para Vendas, pressione ou fale 1. Para Serviços, pressione ou fale 2. Para Suporte ao Cliente, pressione ou fale 3. Para falar com o operador, pressione ou fale 0. Para ouvir este menu novamente, pressione a tecla de asterisco ou fale repetir". **Criar um prompt personalizado** Se você escolher isso, deverá inserir o texto que deseja que o sistema leia (até 1000 caracteres). **Carregar um arquivo de áudio** Se você escolher isso, deverá gravar a saudação e depois carregar o arquivo de áudio (nos formatos .wav, .mp3 ou .wma).|
|**4**|**Discagem por nome** Se você escolher essa opção, isso permitirá que as pessoas que ligarem para pesquisar pessoas em sua organização usando a pesquisa de diretório. Você pode selecionar quais pessoas serão listadas como disponível ou não para discagem por nome, configurando as opções na página **escopo de discagem**. Qualquer usuário com uma licença de **Sistema telefônico** online pode ser encontrado por discagem por nome.> [!CAUTION]> Os usuários hospedados localmente que usam o Skype for Business Server 2015 ou o Lync Server 2013 e o 2010 **não podem ser acessados** com o recurso Discar por Nome.          |
|**5**|**Editar opções de menu** As opções de menu podem ser adicionadas ou removidas usando os botões de tecla no teclado. Para adicionar uma opção de menu, pressione a tecla correspondente no teclado. As teclas em uso mudarão de cor e a linha de opções correspondente será exibida abaixo. Para excluir uma Opção de Menu, basta clicar na tecla correspondente no controle do teclado para desmarcar essa tecla. A linha de mapeamento de tecla será removido.> [!TIP]> Você terá que atualizar o texto dos prompts o menu ou gravar novamente o áudio separadamente durante a adição ou remoção das opções, porque isso não será feito automaticamente para o prompt do menu existente.           Qualquer opção de menu pode ser adicionada e removida em qualquer ordem e os mapeamentos de tecla não têm que ser contínuos. Por exemplo, é possível criar um menu com as teclas 0, 1 e 3 mapeadas para opções, enquanto as teclas 2 não são usadas.> [!NOTE]> As teclas * (Repetir) e # (Voltar) são reservadas pelo sistema e não podem ser reatribuídas. Se o reconhecimento de fala for habilitado, pressionar * corresponderá ao comando de voz "Repetir" e # corresponderá ao comando de voz "Voltar".           |
|**6**| Para configurar as opções do menu, depois que você selecionar a(s) tecla(s), você deverá: **Digitar o nome da opção** Esse nome pode ter até 64 caracteres e pode conter várias palavras como "Atendimento ao Cliente" ou "Operações e Bases ". Se o reconhecimento de fala for habilitado, o nome será reconhecido automaticamente e a pessoa que ligar conseguirá pressionar 3, falar "três" ou falar "Atendimento ao Cliente" para selecionar a opção mapeada para a tecla 3. A próxima etapa é selecionar onde a chamada deve ser enviada se a tecla correspondente será pressionada ou a opção será selecionada usando o reconhecimento de fala. A chamada pode ser enviada para: **Operador** Se o operador já estiver configurado, ele será mapeado automaticamente como a tecla 0, mas ele também poderá ser excluído ou reatribuído a uma outra tecla. Se o operador não for definido para nenhuma tecla, então o comando de voz "Operador" também será desabilitado. Uma **pessoa em sua empresa** que seja um usuário Online com uma licença de **Sistema telefônico** que está habilitada para Enterprise Voice ou atribuído um plano chamar no Office 365. Você pode configurá-lo para a pessoa que estiver ligando possa ser enviada para a caixa postal. Para fazer isso, selecione uma **pessoa na sua empresa** e essa pessoa terá suas chamadas serem encaminhadas diretamente para a caixa postal.> [!NOTE]>  Não há suporte para os usuários hospedados localmente que usam o Skype for Business Server 2015 ou o Lync Server 2013 e o 2010.           Uma **Fila de chamadas** o uso da opção Fila de Chamadas permite que a chamada seja transferida para uma fila de chamadas existente que você configurou. **Atendedor automático** Você pode usar um atendedor automático existente para criar um segundo nível de opções de menu contendo um submenu. Eles são chamados de atendedores automáticos aninhados.> [!NOTE]>  O **Horário Comercial** de atendedores automáticos (ou segundo nível) aninhados também será usado incluindo as chamadas enviadas de outro atendedor automático que foi configurado.          |
   
### Página Selecionar escopo de discagem

Nesta página, você pode configurar quais usuários em sua organização serão listados em seu diretório e estarão disponíveis para o recurso Discar por Nome quando uma pessoa ligar para a organização.
  
![Dial scope for searching with dial by name.](../images/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)
  
|||
|:-----|:-----|
|**1** <br/> | Ao usar a opção **Incluir**, você tem duas opções:  <br/> **Usuários todos Online** Usando essa opção permite todas as pessoas em sua organização a serem incluídos na pesquisa de diretório. Todos os usuários Online com uma licença de **Sistema telefônico** com chamando planos no Office 365 serão listados. <br/> **Personalizado** Se você usar esta opção, você pode procurar por um grupo do Office 365, lista de distribuição ou grupo de segurança que foi criado em sua organização e as pessoas adicionado Este Office 365 grupo, lista de distribuição ou segurança grupo quem são os usuários Online **com um sistema telefônico licença** serão incluídos na pesquisa de diretório. Você pode adicionar vários grupos do Office 365, listas de distribuição e grupos de segurança. <br/> > [!CAUTION]>  Usuários do local de implantações do Skype para Business 2015 ou Lync Server 2013 e 2010 não serão listados quando alguém a pesquisa no diretório usando discagem por nome.          |
|**2** <br/> | Ao usar a opção **Excluir**, você tem duas opções:  <br/> **Nenhuma** O uso desta opção indicará que nenhum usuário online será excluído da pesquisa de diretório. <br/> **Personalizado** Se você usar esta opção, você pode procurar por um grupo do Office 365, grupo de segurança ou lista de distribuição que foi criado em sua organização e todas as pessoas adicionado a esse grupo do Office 365, grupos de segurança ou lista de distribuição serão excluídos da pesquisa de diretório. Você pode adicionar vários grupos do Office 365, listas de distribuição e grupos de segurança. <br/> > [!CAUTION]>  Usuários do local de implantações do Skype para Business 2015 ou Lync Server 2013 e 2010 não serão listados quando alguém a pesquisa no diretório usando discagem por nome.          |
   
> [!NOTE]
> Pode levar até 36 horas para um novo usuário ter seu nome listado no diretório quando alguém usa o Discar por Nome com reconhecimento de fala. 
  
Depois que você preencher todos os campos obrigatórios e configurar os menus e as opções de administração de chamadas, clique em **Salvar**.
  
## Editar e testar atendedores automáticos

Depois de ter salvo o atendedor automático, ele será listado na página **Atendedores automáticos**. Isso permitirá que você veja rapidamente algumas das opções configuradas, incluindo o nome, o número do telefone, o idioma e o status.
  
Se você deseja fazer alterações em um atendedor automático, clique para destacar o atendedor automático no painel lateral, você pode clicar em **Editar**.
  
Você também pode fazer uma chamada de teste rapidamente para o atendedor automático usando o botão **Testar** no painel lateral.
  
## Deseja saber mais?

Você também pode usar o Windows PowerShell para criar e configurar atendedores automáticos.
  
### Cmdlets de atendedores automáticos

Veja os cmdlets necessários para gerenciar um atendedor automático.
  
||||
|:-----|:-----|:-----|
|[New-CsOrganizationalAutoAttendant](https://technet.microsoft.com/en-us/library/mt796493.aspx) <br/> |[Get-CsOrganizationalAutoAttendantSupportedTimeZone]( https://technet.microsoft.com/en-us/library/mt796483.aspx) <br/> |[New-CsOrganizationalAutoAttendantMenu](https://technet.microsoft.com/en-us/library/mt796488.aspx ) <br/> |
|[Set-CsOrganizationalAutoAttendant](https://technet.microsoft.com/en-us/library/mt796486.aspx) <br/> |[Get-CsOrganizationalAutoAttendantSupportedLanguage](https://technet.microsoft.com/en-us/library/mt796481.aspx) <br/> |[New-CsOrganizationalAutoAttendantCallFlow](https://technet.microsoft.com/en-us/library/mt796489.aspx) <br/> |
|[Get-CsOrganizationalAutoAttendant](https://technet.microsoft.com/en-us/library/mt796482.aspx ) <br/> |[New-CsOrganizationalAutoAttendantCallableEntity](https://technet.microsoft.com/en-us/library/mt796480.aspx) <br/> |[New-CsOnlineTimeRange](https://technet.microsoft.com/en-us/library/mt796491.aspx ) <br/> |
|[Remove-CsOrganizationalAutoAttendant](https://technet.microsoft.com/en-us/library/mt796492.aspx) <br/> |[New-CsOrganizationalAutoAttendantPrompt](https://technet.microsoft.com/en-us/library/mt796484.aspx ) <br/> |[New-CsOnlineSchedule](https://technet.microsoft.com/en-us/library/mt796490.aspx) <br/> |
|[New- CsOnlineAudioFile](https://technet.microsoft.com/en-us/library/mt796479.aspx) <br/> |[New-CsOrganizationalAutoAttendantMenuOption](https://technet.microsoft.com/en-us/library/mt796485.aspx ) <br/> |[New-CsOrganizationalAutoAttendantCallHandlingAssociation](https://technet.microsoft.com/en-us/library/mt796487.aspx ) <br/> |
   
### Mais sobre o Windows PowerShell

- O Windows PowerShell serve para o gerenciamento de usuários e do que os usuários podem ou não podem fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Seis motivos para usar o Windows PowerShell para gerenciar o Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Aviso de Isenção de Tradução Automática**: Este artigo foi traduzido por computador, sem intervenção humana. A Microsoft oferece essas traduções automáticas para ajudar as pessoas que não falam inglês a aproveitar os textos escritos sobre produtos, serviços e tecnologias da Microsoft. Como este artigo foi traduzido automaticamente, é possível que contenha erros de vocabulário, sintaxe ou gramática. 
  

