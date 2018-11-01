---
title: Configurar o atendedor automático do Sistema de Telefonia
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.date: 9/1/2018
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'Saiba como configurar e testar os atendedores automáticos de sistema telefônico (nuvem PBX) para eficiente tratamento de chamadas para sua organização. '
ms.openlocfilehash: 0bf312734c788e0bd02bc4fce40dbea4267850d4
ms.sourcegitcommit: 9138325ba2652a9ee3602d259de811082080e358
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/30/2018
ms.locfileid: "25842088"
---
# <a name="set-up-a-phone-system-auto-attendant"></a>Configurar o atendedor automático do Sistema de Telefonia

Atendedores automáticos permitem que as pessoas que ligam para sua organização e navegue para conectá-los ao departamento direita, chame a fila, pessoa ou o operador de um sistema de menus. Você pode criar um atendedor automático para sua organização usando o Skype para o Centro de administração de negócios. Para criar um novo atendedor automático, vá para **Encaminhamento de chamada** na navegação esquerda e depois selecione **Atendedores automáticos** > **Adicionar novo**.

Se você deseja saber mais sobre os atendedores automáticos, consulte [Cite atendedores automáticos de sistema telefônico?](/microsoftteams/what-are-phone-system-auto-attendants)

## <a name="step-1---getting-started"></a>Etapa 1 - Introdução

- Before you can create and set up your auto attendants, you will need to get or transfer your existing toll or toll-free service numbers. Após você fazer a chamada Tarifada ou números gratuitos de serviço, ele serão exibido no **Skype para centro de administração de negócios** > **voz** > página**números de telefone** . Para obter seus números de serviço, consulte [Getting números de telefone de serviço para Skype para equipes da Microsoft e de negócios](getting-service-phone-numbers.md)ou se você deseja transferir e o número de serviço existente, consulte [transferir os números de telefone para o Office 365](/microsoftteams/transfer-phone-numbers-to-office-365). **User (subscriber)** numbers can't be assigned to auto attendants. Se você estiver fora dos Estados Unidos, é possível utilizar o Skype para centro de administração de negócios para obter os números de serviço; Vá [aqui](/microsoftteams/manage-phone-numbers-for-your-organization) em vez disso.

    > [!CAUTION]
    > Para obter e usar números de telefone gratuitos, você precisa configurar Créditos de Comunicação. Para fazer isso, consulte [O que são Créditos de Comunicação?](/microsoftteams/what-are-communications-credits) e [Configurar Créditos de Comunicação para a sua organização](/microsoftteams/set-up-communications-credits-for-your-organization).
  
- Sua organização deve ter (no mínimo), uma licença Enterprise E3 plus **Sistema telefônico** ou uma licença Enterprise E5. O número de licenças de usuário do **Sistema telefônico** atribuídos afeta o número de números de serviço que estão disponíveis a serem usados para atendedores automáticos. Os números dos atendedores automáticos que depende das licenças de **Sistema telefônico** e **Audioconferência** números que são atribuídas em sua organização. Para saber mais sobre licenciamento, vá [aqui](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

    > [!TIP]
    > Para redirecionar chamadas para um operador ou uma opção de menu que é um usuário Online com uma licença de **Sistema telefônico** , você precisará habilitá-los para o Enterprise Voice ou atribuir chamar planos no Office 365 para acessá-los. Consulte [Atribuir Skype para licenças de negócios e equipes da Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Você também pode usar o Windows PowerShell. Por exemplo, execute:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
## <a name="step-2---create-a-new-auto-attendant"></a>Etapa 2 - Criar um novo atendedor automático

 **Usando as equipes da Microsoft & Skype para Business Admin Center**

No **Microsoft equipes & Skype para Business Admin Center**, clique em ![sfb-logotipo-30x30.png](../images/sfb-logo-30x30.png) **Portal herdada** >  **roteamento de chamadas** > **atendedores automáticos**, clique em **+ Adicionar novo**:

### <a name="edit-general-info-page"></a>Editar página de informações gerais

![New auto attendant page 1.](../images/edacec94-9384-4a87-be0a-5c49a151287e.png)

***
![Número 1](../images/sfbcallout1.png)<br/>**Nome** Insira um nome de exibição descritivo para o atendedor automático. O nome é obrigatório e pode conter até 64 caracteres, incluindo espaços. Ele será listado na coluna **Nome** da guia **Atendedores automáticos**.
***

![Número 2](../images/sfbcallout2.png)<br/>**Número de telefone** Essa configuração é opcional. Se desejar, selecione um número de telefone para o atendedor automático. Você pode selecionar qualquer tarifas do serviço disponível ou o número de chamada gratuita que você precisa para sua organização. Se não existirem números de telefone listados, você deverá obter um número de serviço de chamada tarifada e gratuita. Vá [aqui](getting-service-phone-numbers.md) para fazer isso. <br/> <br/>

> [!NOTE]
> **User (subscriber)** numbers can't be assigned to auto attendants.

***
![Número 3](../images/sfbcallout3.png)<br/>**Fuso horário** Você deve definir o fuso horário para o atendedor automático, mas ele não precisa corresponder ao fuso horário do endereço principal de sua organização. Cada atendedor automático pode ter um fuso horário diferente e os horários comerciais definidos para o atendedor automático serão definidos com base no fuso horário que você selecionar aqui.
***
![14](../images/sfbcallout4.png)<br/>**Idioma** Selecione o idioma que você deseja usar para o atendedor automático entre os idiomas disponíveis listados. O idioma que você definir aqui é o idioma que o atendedor automático usará para interagir com pessoas que ligam para este atendedor automático e todo os sistema os avisos serão reproduzidos neste idioma.
***
![Número 5](../images/sfbcallout5.png)<br/>**Reconhecimento de fala** Reconhecimento de fala está disponível e se esta opção está selecionada. Pessoas que chamam no podem usar a entrada de voz no idioma que você definir. Você pode desativar o reconhecimento de fala desmarcando-a se desejar apenas permitir que as pessoas usam do teclado do telefone.
***
![Número 6](../images/sfbcallout6.png)<br/>**Operador** Isso é opcional e não precisa ser definido para o atendedor automático. No entanto, você pode definir a opção de **operador** para pessoas que ligam para ser capaz de quebrar sem os menus para falar com uma pessoa para ajudá-los. <br/> <br/> A tecla 0 é atribuída automaticamente ao Operador. <br/> <br/> Se você configurar isso, você também precisará informar as pessoas a quem chamar que isso é uma opção disponível em **Opções de menu de edição** , na página de **tratamento de chamada do horário comercial** . Se você definir um operador na sua atendedor automático, você precisará inserir o texto de aviso correspondente na caixa **os chamadores ouvirão** ou alterar seu arquivo de áudio para incluir essa opção. Por exemplo, "Para falar com o operador, pressione 0". <br/><br/>  Você pode definir um dos seguintes como Operador: 
*    **Pessoa da sua empresa** com uma licença de **Sistema de Telefonia** habilitada para Enterprise Voice ou com Planos de Chamadas do Office 365 atribuídos. <br/>

     > [!Note] 
     > A **Pessoa da sua empresa** pode ser um usuário Online ou um usuário hospedado no local usando o Skype for Business Server 2015 ou o Lync Server 2013. Não há suporte para Lync Server 2010. <br/> 

* A **Call Queue** that you have set up. 
* Você pode configurá-lo para que a pessoa que liga seja enviada para a caixa postal. Para fazer isso, selecione **a pessoa da sua empresa** e defina as chamadas sejam encaminhadas diretamente para a caixa postal dessa pessoa. 

### <a name="select-hours-of-operation-page"></a>Página Selecionar as horas de operação

Por padrão, o horário comercial é definido para 24 horas por dia, 7 dias por semana, para que todas as horas são consideradas horário comercial. Todos os horários que não estão incluídos nos horários comerciais são considerados horários fora do expediente. Se você selecionar a opção **Personalizar** e definir seu horário comercial, em seguida, uma nova página chamada **após o horário de tratamento de chamada** será adicionada onde você pode configurar a tratamento de chamadas para após o horário comercial para o atendedor automático.

![New auto attendant Hours of operation.](../images/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

***
![Número 1](../images/sfbcallout1.png)<br/>Selecione a opção **Personalizar** para selecionar horários comerciais específicos no calendário. Quando você selecionar **Personalizar**, os horários comerciais serão definidos de segunda a sexta, das 900h às 17h, por padrão.
***
![Número 2](../images/sfbcallout2.png)<br/>Para alterar os horários comerciais, destaque os horários comerciais que deseja definir usando o calendário. O calendário permite que você selecione horários comerciais em intervalos de 30 minutos, e o horário comercial que você selecionar aqui será definido com base no fuso horário que você definiu na página **Geral info** . Para configurar um intervalo (horário de almoço, por exemplo), desmarque ou arraste para desmarcar o horário no calendário. Você pode definir várias quebras em horário comercial. 

### <a name="select-business-hours-call-handling-page"></a>Página selecionar horário comercial de administração de chamadas

> [!TIP]
> [!DICA] Se você usar um cronograma personalizado de horários comerciais, também deverá configurar a administração de chamadas para horários fora do expediente. Uma página **Administração de chamadas após o expediente** será adicionada, portanto, você pode configurar essas opções e você terá as mesmas opções que as de **Administração de chamadas de horários comerciais**. 

Você pode configurar saudações e prompts menus que as pessoas que a chamada no número de telefone do atendedor automático da sua organização ouvirá durante o horário comercial.

![Business hours call handling.](../images/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)

***
![Número 1](../images/sfbcallout1.png)<br/>**Saudação da empresa** A saudação para horário comercial é opcional e pode ser definida como **Nenhuma**. Nesse caso, a pessoa que liga não ouvirá nenhuma mensagem ou saudação antes da chamada ser atendida por uma das opções selecionadas. Você também pode carregar um arquivo de áudio (em formatos .wav, .mp3 ou. wma) ou criar uma saudação personalizada usando conversão de texto em fala.
* **Nenhuma** Nenhuma saudação será reproduzida quando as pessoas ligarem para o número de telefone do atendedor automático.
*    **Criar um sinalizador de saudação** Se você escolher essa opção, insira o texto que você deseja que o sistema para ler (até 1000 caracteres). Por exemplo, você pode inserir "Bem-vindo à Contoso. A sua ligação é muito importante para nós." na caixa **Os chamadores ouvirão**.
* **Carregar um arquivo de áudio** Se você escolher essa opção, gravar a saudação e, em seguida, carregue o seu arquivo de áudio (em um formato. wav,. mp3 ou. wma).
***
![Número 2](../images/sfbcallout2.png)<br/>Você pode selecionar o que acontece às chamadas que chegam durante o horário comercial. Você pode escolher entre as seguintes opções:
* **Desconectar** Se você selecionar a ele, a pessoa chamando em será desconectada depois de ouvir uma saudação para horário comercial.
* **Redirecionar chamada** Isso pode ser usado para enviar a chamada automaticamente para:
  * **Pessoa da sua empresa** com uma licença de **Sistema de Telefonia** habilitada para Enterprise Voice ou com Planos de Chamadas do Office 365 atribuídos. Você pode configurá-lo para que o chamador possa ser enviado para a caixa postal. Para fazer isso, selecione **a pessoa da sua empresa** e defina essa pessoa para que suas chamadas encaminhadas diretamente para a caixa postal. <br/><br/>
    > [!Note]
    > A **Pessoa da sua empresa** pode ser um usuário Online ou um usuário hospedado no local usando o Skype for Business Server 2015 ou o Lync Server 2013. Não há suporte para Lync Server 2010. <br/><br/>

  * Uma **Fila de chamada** usando uma fila de espera de chamadas permite que a chamada seja transferida para uma fila existente chamada que você definiu.
  * Atendedor para criar um segundo nível das opções de menu que contém um submenu automático do outro **atendedor automático** , você pode usar um existente. These are called nested auto attendants.

* **Play menu options prompt** These can also be used to let you set up a prompt you want played.
***
![Número 3](../images/sfbcallout3.png)<br/>**Prompt do menu** Para criar o prompt do menu principal, você pode usar a conversão de texto em fala ou carregar um arquivo de áudio (.wav, .mp3 ou .wma). Você pode digitar o prompt na caixa **Os chamadores ouvirão** ou gravar um arquivo de áudio e dizer, por exemplo: "Para Vendas, pressione ou fale 1. Para Serviços, pressione ou fale 2. Para Suporte ao Cliente, pressione ou fale 3. Para falar com o operador, pressione ou fale 0. Para ouvir este menu novamente, pressione a tecla de asterisco ou fale repetir". **Criar um prompt personalizado** Se você escolher isso, deverá inserir o texto que deseja que o sistema leia (até 1000 caracteres). **Carregar um arquivo de áudio** Se você escolher isso, deverá gravar a saudação e depois carregar o arquivo de áudio (nos formatos .wav, .mp3 ou .wma).
***
![Número 4](../images/sfbcallout4.png)<br/>**Discagem por nome** Se você escolher essa opção, isso permitirá que as pessoas que ligam para pesquisar por pessoas em uma organização usando a pesquisa de diretório. Você pode selecionar as pessoas que serão listadas como disponíveis ou indisponíveis para Discagem por Nome na página **Escopo de discagem**. Qualquer usuário online com uma licença de **Sistema de Telefonia** ou hospedado no local usando o Skype for Business Server 2015 ou o Lync Server 2013 pode ser encontrado com a Discagem por Nome.<br/><br/>  

> [!WARNING]
> Usuários hospedados no local usando o Lync 2010 **não podem ser acessados** com a Discagem por Nome.
> ***

![Número 5](../images/sfbcallout5.png)<br/>**Edit menu options** Menu options can be added or removed by using key buttons on the keypad. Para acrescentar uma opção, pressione a tecla correspondente no teclado. The keys in use will change in color and the corresponding row of options will appear below. Para excluir uma opção de menu, basta clicar na tecla de correspondente no controle do teclado para desmarcar essa chave. A linha de mapeamento de teclas será removida.<br/><br/>  **Dica:** Você precisará atualizar o texto de prompts de menu ou gravar novamente o áudio separadamente ao adicionar a removendo opções porque ele não será feito automaticamente para o prompt do menu existente.  <br/><br/>  Qualquer opção de menu pode ser adicionada e removida em qualquer ordem, e os mapeamentos de teclas não precisam ser contínuo. Por exemplo, é possível, para criar um menu com as teclas de 0, 1 e 3 mapeadas para opções, enquanto a tecla 2 não será usada.<br/><br/> 

> [!NOTE]
> As teclas * (Repetir) e # (Voltar) são reservadas pelo sistema e não podem ser reatribuídas. Se o reconhecimento de fala estiver habilitado, pressionando * corresponderá com "Repetir" e # corresponderá com os comandos de voz "Volta".


Para configurar suas opções de menu, após selecionar as teclas, você precisará: 
- **Digite o nome da opção** Isso pode ter até 64 caracteres de comprimento e pode conter várias palavras como "E atendimento"ao cliente ou"operações pó." Se o reconhecimento de fala está habilitado, o nome será reconhecido automaticamente e a pessoa chamando em poderão Pressione 3, diga "três", ou dizer "Atendimento ao cliente" para selecionar a opção mapeada para a tecla 3. 
- A próxima etapa é selecionar para onde a chamada será enviada se a tecla correspondente for pressionada ou selecionada usando o reconhecimento de fala. A chamada pode ser enviada para: 
    - **Operador** Se operador já estiver configurado, ele é mapeado automaticamente a chave 0, mas ele também pode ser excluído ou reatribuído a uma chave diferente. If operator isn't set to any key, then the voice command "Operator" will be disabled too. 
    - Uma **Pessoa da sua empresa** com uma licença de **Sistema de Telefonia** habilitada para Enterprise Voice ou com um Plano de Chamadas do Office 365 atribuído. Você pode configurá-lo para que o chamador possa ser enviado para a caixa postal. Para fazer isso, selecione **a pessoa da sua empresa** e defina essa pessoa para que suas chamadas encaminhadas diretamente para a caixa postal.<br/><br/> 

        > [!Note] 
        > A **Pessoa da sua empresa** pode ser um usuário Online ou um usuário hospedado no local usando o Skype for Business Server 2015 ou o Lync Server 2013. Não há suporte para Lync Server 2010. <br/><br/>

    - **Fila de chamadas** Usar uma opção de fila de chamada permite que a chamada seja transferida para uma fila de chamada existente que você definiu. 
    - **Auto Attendant** You can use an existing auto attendant to create a second level of menu options containing a submenu. These are called nested auto attendants.<br/><br/>

        > [!Note]
        > O **horário comercial** de atendedores automáticos aninhados (ou segundo nível) também será usada, incluindo para as chamadas enviadas a partir de outros atendedores automáticos que foram configurados.

### <a name="select-holidays-page"></a>Página selecionar feriados

Você pode adicionar até 20 feriados agendados para cada atendedor automático.

![Configurar feriados no atendedor automático](../images/50a5ce88-7f39-4210-808a-da7ced969854.png)

***
![Número 1](../images/sfbcallout1.png)<br/>**Adicionar um feriado** Insira um nome para seu novo feriado no campo **Nome do feriado**.<br/><br/> Os nomes de feriados podem ter até 64 caracteres e devem ser únicos para o mesmo atendedor automático. Por exemplo, você não pode ter dois feriados com o nome "Ação de Graças" no mesmo atendedor automático.  
***
![Número 2](../images/sfbcallout2.png)<br/>**Saudação de feriado** A saudação de feriado é opcional e pode ser definida como **Nenhuma**. Nesse caso, a pessoa que liga não ouvirá nenhuma mensagem ou saudação antes da chamada ser atendida por uma das opções selecionadas. Você também pode carregar um arquivo de áudio (em formatos .wav, .mp3 ou. wma) ou criar uma saudação personalizada usando conversão de texto em fala.
* **Nenhuma** Nenhuma saudação será reproduzida quando as pessoas ligarem para o número de telefone do atendedor automático.
* **Criar um sinalizador de saudação** Se você escolher essa opção, insira o texto que você deseja que o sistema para ler (até 1000 caracteres). Por exemplo, você pode inserir "Feliz ano novo! Nossos escritórios estão fechados no momento." na caixa **Os chamadores ouvirão**.
* **Carregar um arquivo de áudio** Se você escolher essa opção, gravar a saudação de feriado e, em seguida, carregue o seu arquivo de áudio (em um formato. wav,. mp3 ou. wma).  
***
![Número 3](../images/sfbcallout3.png)<br/>**O que acontece com as chamadas após a saudação?** Você pode selecionar o que acontece com as chamadas que chegam durante este feriado. Você pode escolher entre as seguintes opções:
* **Desconectar** A pessoa será desconectada após ouvir a saudação de feriado.
* **Redirecionar chamada** Isso pode ser usado para enviar a chamada automaticamente para:
  * Uma **Pessoa da sua empresa** com uma licença de **Sistema de Telefonia** habilitada para Enterprise Voice ou com Planos de Chamadas do Office 365 atribuídos. Você pode configurá-lo para que o chamador possa ser enviado para a caixa postal. Para fazer isso, selecione a **pessoa na sua empresa**e defina essa pessoa para que suas chamadas encaminhadas diretamente para a caixa postal. <br/><br/> 

    > [!Note] 
    > A **Pessoa da sua empresa** pode ser um usuário Online ou um usuário hospedado no local usando o Skype for Business Server 2015 ou o Lync Server 2013. Não há suporte para Lync Server 2010.<br/><br/>

  * Uma **Fila de chamadas** para transferir a chamada para uma fila existente chamada que você definiu.
  * Outro **atendedor automático**, para criar um segundo nível das opções de menu que contém um submenu. These are called nested auto attendants. <br/><br/>

    > [!Note]
    > Por padrão, todas as chamadas recebidas durante um período de feriado desconectam a pessoa após a saudação (se houver uma), portanto, você deve especificar um redirecionamento caso outro comportamento seja desejado.

***
![Número 4](../images/sfbcallout4.png)<br/>**Quando você deseja que o feriado inicie e termine?** Insira a data de início do feriado no formato dd/mm/aaaa e selecione uma hora de início e data e hora de término, conforme solicitado na tabela de intervalo de data.<br/><br/>Você pode especificar até 10 intervalos de data para um feriado. Por exemplo, você pode adicionar intervalos de data para feriados de ano novo para até 10 anos. Um feriado pode abranger vários dias.<br/><br/>Para adicionar intervalos de datas de feriados adicionais (por exemplo, para o ano seguinte), clique em **Adicionar outro** e, em seguida, insira um novo conjunto de datas de início e término do feriado.<br/><br/>Também há suporte para feriados aninhados. Por exemplo, você pode aninhar vários feriados em um único período de tempo de "pausa para feriado": 
* **De 24 de dezembro até 3 de janeiro:** "Boas festas! Nossos escritórios estão fechados no momento. Reabriremos no dia 4 de janeiro."
* **25 de dezembro:** "Feliz Natal! Nossos escritórios estão fechados no momento. Reabriremos no dia 4 de janeiro."
* **1º de janeiro:** "Feliz ano novo! Nossos escritórios estão fechados no momento. Reabriremos no dia 4 de janeiro."

Depois de salvar seu atendedor automático, os feriados aparecem na guia **Feriados**, onde você pode editar, adicionar ou modificar as configurações de feriado.

### <a name="select-dial-scope-page"></a>Página Selecionar escopo de discagem

Nesta página, você pode configurar quais usuários em sua organização poderão ser listados no diretório e disponíveis para discagem pelo nome quando uma pessoa que chama em sua organização.

![Dial scope for searching with dial by name.](../images/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)

***
![Número 1](../images/sfbcallout1.png)<br/>Ao usar a opção **Incluir**, você tem duas opções:
* **Todos os usuários online** O uso dessa opção permite que todas as pessoas da organização sejam incluídas na pesquisa do diretório. Todos os usuários Online com uma licença de **Sistema de Telefonia**, bem como os usuários hospedados no local que usam o Skype for Business Server 2015 ou o Lync Server 2013, que têm Planos de Chamadas no Office 365, serão listados. 
* **Personalizado** Se usar essa opção, você pode pesquisar um Grupo do Office 365, uma lista de distribuição ou um grupo de segurança criado na sua organização e as pessoas adicionadas no Grupo do Office 365, na lista de distribuição ou no grupo de segurança que são **Usuários Online com uma licença do Sistema de Telefonia** ou estão hospedados no local usando o Skype for Business Server 2015 ou o Lync Server 2013. Você pode adicionar vários grupos do Office 365, listas de distribuição e grupos de segurança. <br/><br/> 

  > [!Caution]
  > Usuários locais de implantações do Lync Server 2010 não listados quando alguém pesquisará o diretório usando discagem por nome. 
***
![Número 2](../images/sfbcallout2.png)<br/>Usando a opção **Excluir** , você tem duas opções:
* **Nenhuma** O uso desta opção indicará que nenhum usuário online será excluído da pesquisa de diretório. 
* **Sinalizador** Se você usar essa opção, você pode procurar um grupo do Office 365, lista de distribuição ou grupo de segurança que foi criado em sua organização, e todas as pessoas adicionado a esse grupo do Office 365, lista de distribuição ou grupos de segurança serão excluídos da pesquisa de diretório. Você pode adicionar vários grupos do Office 365, listas de distribuição e grupos de segurança. <br/><br/> 

  > [!Caution]
  > Usuários locais de implantações do Lync Server 2010 não listados quando alguém pesquisará o diretório usando discagem por nome.

> [!NOTE]
> Poderá demorar até 36 horas para um novo usuário ter seu nome listado no diretório quando alguém usa discagem pelo nome, com reconhecimento de fala. 

Depois de inserir todos os campos necessários e configurar opções e menus de tratamento de chamada, clique em **Salvar**.

## <a name="editing-and-testing-auto-attendants"></a>Edição e testes atendedores automáticos

Depois de ter salvo o atendedor automático, ele será listado na página **Atendedores automáticos**. Isso permitirá que você veja rapidamente algumas das opções que você definiu, incluindo o nome, número de telefone, idioma e status.

Se desejar fazer alterações em um atendedor automático, selecione o atendedor automático e, em seguida, no painel de ações, clique em **Editar**.

Também rapidamente, você pode colocar uma chamada de teste para o atendedor automático usando o botão **Testar** no painel ação.

## <a name="want-to-know-more"></a>Deseja saber mais?

Você também pode usar o Windows PowerShell para criar e configurar atendedores automáticos.

### <a name="auto-attendant-cmdlets"></a>Cmdlets de atendedores automáticos

Veja os cmdlets necessários para gerenciar um atendedor automático.

|| |
|---  |---  |
| [New-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796493.aspx) | [New-CsOrganizationalAutoAttendantPrompt](https://technet.microsoft.com/library/mt796484.aspx) |
| [Set-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796486.aspx) | [New-CsOrganizationalAutoAttendantMenuOption](https://technet.microsoft.com/library/mt796485.aspx) |
| [Get-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796482.aspx) | [Get-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/get-csorganizationalautoattendantholidays?view=skype-ps) |
| [Remove-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796492.aspx) | [New-CsOrganizationalAutoAttendantMenu](https://technet.microsoft.com/library/mt796488.aspx) |
| [New- CsOnlineAudioFile](https://technet.microsoft.com/library/mt796479.aspx) | [New-CsOrganizationalAutoAttendantCallFlow](https://technet.microsoft.com/library/mt796489.aspx) |
| [Export-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps) | [New-CsOnlineTimeRange](https://technet.microsoft.com/library/mt796491.aspx) |
| [New-CsOnlineDateTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps) | [New-CsOnlineSchedule](https://technet.microsoft.com/library/mt796490.aspx) |
| [Get-CsOrganizationalAutoAttendantSupportedTimeZone](https://technet.microsoft.com/library/mt796483.aspx) | [New-CsOrganizationalAutoAttendantCallHandlingAssociation](https://technet.microsoft.com/library/mt796487.aspx) |
| [Get-CsOrganizationalAutoAttendantSupportedLanguage](https://technet.microsoft.com/library/mt796481.aspx) | [Import-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/import-csorganizationalautoattendantholidays?view=skype-ps) |
| [New-CsOrganizationalAutoAttendantCallableEntity](https://technet.microsoft.com/library/mt796480.aspx) | |

### <a name="more-about-windows-powershell"></a>Mais sobre o Windows PowerShell

- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:

  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:

  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Tópicos relacionados
[Veja aqui o que é fornecido com o Sistema de Telefonia no Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Obtendo números de telefone de serviço do Skype for Business e do Microsoft Teams](getting-service-phone-numbers.md)

[Disponibilidade da Audioconferência e dos Planos de Chamadas por país e região](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[O que são atendedores automáticos do Sistema de Telefonia?](/MicrosoftTeams/what-are-phone-system-auto-attendants.md)

[Exemplo de pequenos negócios - configurar um atendedor automático](tutorial-org-aa.yml)  
