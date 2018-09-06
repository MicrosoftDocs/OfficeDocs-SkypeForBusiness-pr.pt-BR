---
title: Configurar um atendedor automático do Sistema de Telefonia
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Phone System
description: 'Saiba como configurar e testar atendedores automáticos do Sistema de Telefonia (Cloud PBX) para administração eficiente de chamadas em sua organização. '
ms.openlocfilehash: fb35e36e7d59a3d47584fd15e592f68dd3ac4ae5
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2018
ms.locfileid: "23780459"
---
# <a name="set-up-a-phone-system-auto-attendant"></a>Configurar um atendedor automático do Sistema de Telefonia

Os atendedores automáticos permitem que as pessoas que ligam para sua organização naveguem pelo sistema de menus e as direciona para o departamento, fila de chamada, pessoa ou operador certo. Você pode criar um atendedor automático para a sua organização usando o centro de administração do Skype for Business. Para criar um novo atendedor automático, acesse **Encaminhamento de chamada** no painel de navegação esquerdo e depois selecione **Atendedores automáticos** > **Adicionar novo**.
  
Se quiser saber mais sobre os atendedores automáticos, consulte [O que são atendedores automáticos do Sistema de Telefonia?](/microsoftteams/what-are-phone-system-auto-attendants)
  
## <a name="step-1---getting-started"></a>Etapa 1 - Introdução

- Antes de poder criar e configurar atendedores automáticos, você precisa obter números de serviço gratuitos ou pagos, ou transferir os já existentes. Após obtê-los, eles serão exibidos na página **Centro de administração do Skype for Business** > **Voz** > **Números de telefone**. Para obter os números de serviço, consulte [Obter números de telefone de serviço para Skype for Business e Microsoft Teams](getting-service-phone-numbers.md), ou se você deseja transferir um número de serviço existente, consulte [Transferir números de telefone para o Office 365](/microsoftteams/transfer-phone-numbers-to-office-365). Números de **usuário (assinante)** não podem ser atribuídos a atendedores automáticos. Se você estiver fora dos Estados Unidos, não é possível utilizar o centro de administração do Skype for Business para obter números de serviço; em vez disso, vá [aqui](/microsoftteams/manage-phone-numbers-for-your-organization).
    
    > [!CAUTION]
    > Para obter e usar números de telefone gratuitos, você precisa configurar Créditos de Comunicação. Para fazer isso, consulte [O que são Créditos de Comunicação?](/microsoftteams/what-are-communications-credits) e [Configurar Créditos de Comunicação para a sua organização](/microsoftteams/set-up-communications-credits-for-your-organization). 
  
- Sua organização deve ter (no mínimo) uma licença de **Sistema de Telefonia** Enterprise E3 plus ou Enterprise E5. O número de licenças de usuário do **Sistema de Telefonia** atribuídas afeta o número de números de serviço disponíveis para uso com atendedores automáticos. Os números dos atendedores automáticos que você pode ter depende do número de licenças de **Sistema de Telefonia** e **Audioconferência** atribuídos em sua organização. Para saber mais sobre o licenciamento, vá [aqui](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
    > [!TIP]
    > Para redirecionar chamadas para um operador ou uma opção de menu que é um usuário Online com uma licença de **Sistema de Telefonia**, você precisa habilitá-los para o Enterprise Voice ou atribuir Planos de Chamadas no Office 365. Veja [Atribuir licenças do Skype for Business e do Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Você também pode usar o Windows PowerShell. Por exemplo, execute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true` 
  
## <a name="step-2---create-a-new-auto-attendant"></a>Etapa 2 - Criar um novo atendedor automático

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Usar o centro de administração do Skype for Business**


No **Centro de administração do Skype for Business**, clique em **Encaminhamento de chamadas** > **Atendedores Automáticos** e clique em **Adicionar novas**:
  
### <a name="edit-general-info-page"></a>Editar página de informações gerais
  
![Novo atendedor automático página 1.](../images/edacec94-9384-4a87-be0a-5c49a151287e.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>**Nome** Insira um nome descritivo para exibição do atendedor automático. O nome é obrigatório e pode ter até 64 caracteres, incluindo espaços. Ele será listado na coluna **Nome** da guia **Atendedores automáticos**.
***

![Número 2](../images/sfbcallout2.png)<br/>**Número de telefone** Essa configuração é opcional. Se desejar, selecione um número de telefone para o atendedor automático. Você pode selecionar qualquer número de telefone de serviço gratuito ou pago que você tenha na sua organização. Se não houver nenhum número de telefone listado, você precisará obter um número de serviço gratuito ou pago. Vá [aqui](getting-service-phone-numbers.md) para fazer isso. <br/> <br/>

> [!NOTE]
> **Usuário (assinante)** números não podem ser atribuídos a atendedores automáticos.
    
***
![Número 3](../images/sfbcallout3.png)<br/>**Fuso horário** Você deve definir o fuso horário para o atendedor automático, mas ele não precisa corresponder ao fuso horário do endereço principal de sua organização. Cada atendedor automático pode ter um fuso horário diferente e os horários comerciais definidos para o atendedor automático serão definidos com base no fuso horário que você selecionar aqui.
***
![14](../images/sfbcallout4.png)<br/>**Idioma** Selecione o idioma que você deseja usar com o atendedor automático, entre os idiomas disponíveis listados. O idioma definido aqui será usado pelo atendedor automático para interagir com as pessoas que ligarem para ele, e todos os prompts do sistema serão reproduzidos nesse mesmo idioma.
***
![Número 5](../images/sfbcallout5.png)<br/>**Reconhecimento de fala** O reconhecimento de fala está disponível e, se esta opção for marcada, as pessoas que ligam podem usar comandos de voz no idioma definido. Você pode desabilitar o reconhecimento de fala desmarcando essa opção caso deseje que as pessoas usem somente o teclado do telefone.
***
![Número 6](../images/sfbcallout6.png)<br/>**Operador** Isso é opcional e não precisa ser definido para o atendedor automático. No entanto, você pode definir a opção **Operador** para que as pessoas consigam sair do menu e falar com uma pessoa para ajudá-las. <br/> <br/> A tecla 0 é atribuída automaticamente ao Operador. <br/> <br/> Se você configurar isso, também precisa informar as pessoas de que esta é uma opção disponível em **Editar opções de menu** na página **Administração de chamadas no horário comercial**. Se você definir um operador em seu atendedor automático, deverá inserir o texto de solicitação correspondente na caixa **Os chamadores ouvirão** ou alterar o arquivo de áudio para incluir esta opção. Por exemplo, "Para falar com o operador, pressione 0". <br/><br/>  Você pode definir um dos seguintes como Operador: 
*    **Pessoa da sua empresa** com uma licença de **Sistema de Telefonia** habilitada para Enterprise Voice ou com Planos de Chamadas do Office 365 atribuídos. <br/>

        > [!Note] 
        > A **Pessoa da sua empresa** pode ser um usuário Online ou um usuário hospedado no local usando o Skype for Business Server 2015 ou o Lync Server 2013. Não há suporte para Lync Server 2010. <br/> 

*    Uma **Fila de Chamadas** configurada. 
*    Você pode configurá-la para enviar a pessoa que liga para a caixa postal. Para fazer isso, selecione **Pessoa da sua empresa** e defina que as chamadas dessa pessoa serão encaminhadas diretamente para a caixa postal. 
   
### <a name="select-hours-of-operation-page"></a>Página selecionar horário de funcionamento

Por padrão, o horário comercial é definido como 24 por dia, 7 dias por semana; portanto, todos os horários são considerados horário comercial. Todos os horários que não estão incluídos no horário comercial são considerados horários fora do expediente. Se você selecionar a opção **Personalizar** e definir o seu horário comercial, uma nova página chamada **Administração de chamadas fora do expediente** será adicionada, na qual você pode configurar a administração de chamadas do o atendedor automático para o horário fora do experiente.
  
![Novo horário de funcionamento do atendedor automático.](../images/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

***
![Número 1](../images/sfbcallout1.png)<br/>Selecione a opção **Personalizar** para selecionar horários comerciais específicos no calendário. Quando você selecionar **Personalizar**, os horários comerciais serão definidos de segunda a sexta, das 900h às 17h, por padrão.
***
![Número 2](../images/sfbcallout2.png)<br/>Para alterar o horário comercial, destaque o horário que deseja definir usando o calendário. O calendário permite selecionar horários em intervalos de 30 minutos, e o horário comercial selecionado aqui é baseado no fuso horário que você definir na página **Informações gerais**. Para configurar um intervalo (horário de almoço, por exemplo), desmarque o horário no calendário ou arraste-o até desmarcar. Você pode definir vários intervalos durante o horário comercial. 
   
### <a name="select-business-hours-call-handling-page"></a>Página selecionar horário comercial de administração de chamadas

> [!TIP]
> [!DICA] Se você usar um cronograma personalizado de horários comerciais, também deverá configurar a administração de chamadas para horários fora do expediente. Uma página **Administração de chamadas após o expediente** será adicionada, portanto, você pode configurar essas opções e você terá as mesmas opções que as de **Administração de chamadas de horários comerciais**. 
  
Você pode configurar saudações, solicitações e menus para as pessoas que ligarem para o número de telefone do atendedor automático da sua organização ouvirem durante o horário comercial.
  
![Administração de chamadas em horário comercial.](../images/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>**Saudação da empresa** A saudação para horário comercial é opcional e pode ser definida como **Nenhuma**. Nesse caso, a pessoa que liga não ouvirá nenhuma mensagem ou saudação antes da chamada ser atendida por uma das opções selecionadas. Você também pode carregar um arquivo de áudio (em formatos .wav, .mp3 ou. wma) ou criar uma saudação personalizada usando conversão de texto em fala.
*    **Nenhuma** Nenhuma saudação será reproduzida quando as pessoas ligarem para o número de telefone do atendedor automático.
*    **Criar uma saudação personalizada** Se você escolher essa opção, insira o texto que você deseja que o sistema leia (até 1000 caracteres). Por exemplo, você pode inserir "Bem-vindo à Contoso. A sua ligação é muito importante para nós." na caixa **Os chamadores ouvirão**.
*    **Carregar um arquivo de áudio** Se você escolher essa opção, grave a saudação e carregue o arquivo de áudio (nos formatos .wav, .mp3 ou .wma).
***
![Número 2](../images/sfbcallout2.png)<br/>Você pode selecionar o que acontece com ligações recebidas durante o horário comercial. Você pode escolher entre as seguintes opções:
*    **Desconectar** Se você selecionar isso, a pessoa será desconectada depois de ouvir uma saudação para horário comercial.
*    **Redirecionar chamada** Isso pode ser usado para enviar a chamada automaticamente para:
     *    **Pessoa da sua empresa** com uma licença de **Sistema de Telefonia** habilitada para Enterprise Voice ou com Planos de Chamadas do Office 365 atribuídos. Você pode configurar de maneira que a pessoa seja encaminhada para a caixa postal. Para fazer isso, selecione **Pessoa da sua empresa** e defina que as chamadas dessa pessoa serão encaminhadas diretamente para a caixa postal. <br/><br/>   
        > [!Note]
        > A **Pessoa da sua empresa** pode ser um usuário Online ou um usuário hospedado no local usando o Skype for Business Server 2015 ou o Lync Server 2013. Não há suporte para Lync Server 2010. <br/><br/>

     *    Uma **Fila de Chamadas** A opção Fila de Chamadas permite que a chamada seja transferida para um fila existente já configurada.
     *    Outro **Atendedor Automático** Você pode usar um atendedor existente para criar um segundo nível de opções de menu contendo um submenu. Isso se chama atendedor automático aninhado.
*    **Reproduzir solicitações do menu de opções** Isso também pode ser usado para configurar uma solicitação que você queira que seja reproduzida.
***
![Número 3](../images/sfbcallout3.png)<br/>**Prompt do menu** Para criar o prompt do menu principal, você pode usar a conversão de texto em fala ou carregar um arquivo de áudio (.wav, .mp3 ou .wma). Você pode digitar o prompt na caixa **Os chamadores ouvirão** ou gravar um arquivo de áudio e dizer, por exemplo: "Para Vendas, pressione ou fale 1. Para Serviços, pressione ou fale 2. Para Suporte ao Cliente, pressione ou fale 3. Para falar com o operador, pressione ou fale 0. Para ouvir este menu novamente, pressione a tecla de asterisco ou fale repetir". **Criar um prompt personalizado** Se você escolher isso, deverá inserir o texto que deseja que o sistema leia (até 1000 caracteres). **Carregar um arquivo de áudio** Se você escolher isso, deverá gravar a saudação e depois carregar o arquivo de áudio (nos formatos .wav, .mp3 ou .wma).
***
![Número 4](../images/sfbcallout4.png)<br/>**Discagem por Nome** Escolher essa opção permite quem ligar pesquisar pessoas da sua organização usando o Diretório de Pesquisa. Você pode selecionar as pessoas que serão listadas como disponíveis ou indisponíveis para Discagem por Nome na página **Escopo de discagem**. Qualquer usuário online com uma licença de **Sistema de Telefonia** ou hospedado no local usando o Skype for Business Server 2015 ou o Lync Server 2013 pode ser encontrado com a Discagem por Nome.<br/><br/>  

> [!WARNING]
> Usuários hospedados no local usando o Lync 2010 **não podem ser acessados** com a Discagem por Nome.
***

![Número 5](../images/sfbcallout5.png)<br/>**Editar opções de menu** É possível adicionar ou remover opções do menu usando o teclado numérico. Para acrescentar uma opção, pressione a tecla correspondente no teclado. As teclas em uso mudarão de cor e a linha de opções correspondente aparecerá abaixo. Para excluir uma opção do menu, basta clicar na tecla correspondente no controle do teclado para anular a sua seleção. A linha de mapeamento de teclas será removida.<br/><br/>  **Dica:** Você precisará atualizar o texto das solicitações do menu ou gravar novamente o áudio separadamente ao adicionar ou remover opções, já que isso não será feito automaticamente para as solicitações existentes do menu.  <br/><br/>  Qualquer opção pode ser adicionada ou removida do menu em qualquer ordem, e o mapeamento de teclas não precisa ser contínuo. Por exemplo, é possível criar um menu com as teclas 0, 1 e 3 mapeadas para opções e não usar a tecla 2.<br/><br/> 

> [!NOTE]
> As teclas * (Repetir) e # (Voltar) são reservadas pelo sistema e não podem ser reatribuídas. Se o reconhecimento de fala estiver habilitado, a tecla * corresponderá ao comando de voz "Repetir", e # ao comando "Voltar".


Para configurar suas opções de menu, após selecionar as teclas, você precisará: 
- **Inserir o Nome da opção** Ele pode ter até 64 caracteres e conter várias palavras, como "Atendimento ao cliente" ou "Operações e Justificativas". Se o reconhecimento de voz estiver habilitado, o nome será reconhecido automaticamente e a pessoa poderá pressionar 3, ou dizer "três", ou dizer "Atendimento ao cliente" para selecionar a opção mapeada para a tecla 3. 
- A próxima etapa é selecionar para onde a chamada será enviada se a tecla correspondente for pressionada ou selecionada usando o reconhecimento de fala. A chamada pode ser enviada para: 
    - Um **Operador** Se o operador já estiver configurado, ele é mapeado automaticamente para a tecla 0, mas também pode ser excluído ou reatribuído a uma tecla diferente. Se o operador não tiver uma tecla definida, o comando de fala "Operador" também será desabilitado. 
    - Uma **Pessoa da sua empresa** com uma licença de **Sistema de Telefonia** habilitada para Enterprise Voice ou com um Plano de Chamadas do Office 365 atribuído. Você pode configurar de maneira que a pessoa seja encaminhada para a caixa postal. Para fazer isso, selecione **Pessoa da sua empresa** e defina que as chamadas dessa pessoa serão encaminhadas diretamente para a caixa postal.<br/><br/> 
    
        > [!Note] 
        > A **Pessoa da sua empresa** pode ser um usuário Online ou um usuário hospedado no local usando o Skype for Business Server 2015 ou o Lync Server 2013. Não há suporte para Lync Server 2010. <br/><br/>

    - Uma **Fila de Chamadas** A opção fila de chamadas permite que a chamada seja transferida para um fila existente já configurada. 
    - Um**Atendedor Automático** Você pode usar um atendedor existente para criar um segundo nível de opções de menu contendo um submenu. Isso se chama atendedor automático aninhado.<br/><br/>
    
        > [!Note]
        > O **Horário Comercial** de atendedores automáticos aninhados (ou de segundo nível) também será usado, inclusive para chamadas recebidas de outros atendedores automáticos configurados.         
   
### <a name="select-holidays-page"></a>Página selecionar feriados 

Você pode adicionar até 20 feriados agendados para cada atendedor automático.
  
![Configurar feriados no atendedor automático](../images/50a5ce88-7f39-4210-808a-da7ced969854.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>**Adicionar um feriado** Insira um nome para seu novo feriado no campo **Nome do feriado**.<br/><br/> Os nomes de feriados podem ter até 64 caracteres e devem ser únicos para o mesmo atendedor automático. Por exemplo, você não pode ter dois feriados com o nome "Ação de Graças" no mesmo atendedor automático.  
***
![Número 2](../images/sfbcallout2.png)<br/>**Saudação de feriado** A saudação de feriado é opcional e pode ser definida como **Nenhuma**. Nesse caso, a pessoa que liga não ouvirá nenhuma mensagem ou saudação antes da chamada ser atendida por uma das opções selecionadas. Você também pode carregar um arquivo de áudio (em formatos .wav, .mp3 ou. wma) ou criar uma saudação personalizada usando conversão de texto em fala.
*    **Nenhuma** Nenhuma saudação será reproduzida quando as pessoas ligarem para o número de telefone do atendedor automático.
*    **Criar uma saudação personalizada** Se você escolher essa opção, insira o texto que você deseja que o sistema leia (até 1000 caracteres). Por exemplo, você pode inserir "Feliz ano novo! Nossos escritórios estão fechados no momento." na caixa **Os chamadores ouvirão**.
*    **Carregar um arquivo de áudio** Se você escolher essa opção, grave a saudação de feriado e carregue o arquivo de áudio (nos formatos .wav, .mp3 ou .wma).  
***
![Número 3](../images/sfbcallout3.png)<br/>**O que acontece com as chamadas após a saudação?** Você pode selecionar o que acontece com as chamadas recebidas durante esse feriado. Você pode escolher entre as seguintes opções:
*    **Desconectar** A pessoa será desconectada após ouvir a saudação de feriado.
*    **Redirecionar chamada** Isso pode ser usado para enviar a chamada automaticamente para:
     *    Uma **Pessoa da sua empresa** com uma licença de **Sistema de Telefonia** habilitada para Enterprise Voice ou com Planos de Chamadas do Office 365 atribuídos. Você pode configurar de maneira que a pessoa seja encaminhada para a caixa postal. Para fazer isso, selecione **Pessoa da sua empresa** e defina que as chamadas dessa pessoa serão encaminhadas diretamente para a caixa postal. <br/><br/> 
     
         > [!Note] 
         > A **Pessoa da sua empresa** pode ser um usuário Online ou um usuário hospedado no local usando o Skype for Business Server 2015 ou o Lync Server 2013. Não há suporte para Lync Server 2010.<br/><br/>

     *    Uma **Fila de Chamadas** para transferir a chamada para um fila existente já configurada.
     *    Outro **Atendedor Automático**, para criar um segundo nível de opções de menu contendo um submenu. Isso se chama atendedor automático aninhado. <br/><br/>
     
         > [!Note]
         > Por padrão, todas as chamadas recebidas durante um período de feriado desconectam a pessoa após a saudação (se houver uma), portanto, você deve especificar um redirecionamento caso outro comportamento seja desejado.

***
![Número 4](../images/sfbcallout4.png)<br/>**Quando você deseja que o feriado inicie e termine?** Insira a data de início do feriado no formato dd/mm/aaaa e selecione uma hora de início e data e hora de término, conforme solicitado na tabela de intervalo de data.<br/><br/>Você pode especificar até 10 intervalos de data para um feriado. Por exemplo, você pode adicionar intervalos de data para feriados de ano novo para até 10 anos. Um feriado pode abranger vários dias.<br/><br/>Para adicionar intervalos de datas de feriados adicionais (por exemplo, para o ano seguinte), clique em **Adicionar outro** e, em seguida, insira um novo conjunto de datas de início e término do feriado.<br/><br/>Também há suporte para feriados aninhados. Por exemplo, você pode aninhar vários feriados em um único período de tempo de "pausa para feriado": 
*    **De 24 de dezembro até 3 de janeiro:** "Boas festas! Nossos escritórios estão fechados no momento. Reabriremos no dia 4 de janeiro."
*    **25 de dezembro:** "Feliz Natal! Nossos escritórios estão fechados no momento. Reabriremos no dia 4 de janeiro."
*    **1º de janeiro:** "Feliz ano novo! Nossos escritórios estão fechados no momento. Reabriremos no dia 4 de janeiro."
   
Depois de salvar seu atendedor automático, os feriados aparecem na guia **Feriados**, onde você pode editar, adicionar ou modificar as configurações de feriado.
  
### <a name="select-dial-scope-page"></a>Página selecionar escopo de discagem

Nesta página, você pode configurar quais usuários em sua organização serão listados em seu diretório e estarão disponíveis para o recurso Discagem por Nome quando uma pessoa ligar para a organização.
  
![Escopo de discagem para pesquisa usando discagem por nome.](../images/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/>Ao usar a opção **Incluir**, você tem duas opções:
*    **Todos os usuários Online** Essa opção permite que todas as pessoas da organização sejam incluídas na pesquisa do diretório. Todos os usuários Online com uma licença de **Sistema de Telefonia**, bem como os usuários hospedados no local que usam o Skype for Business Server 2015 ou o Lync Server 2013, que têm Planos de Chamadas no Office 365, serão listados. 
*    **Personalizado** Se usar essa opção, você pode pesquisar um Grupo do Office 365, uma lista de distribuição ou um grupo de segurança criado na sua organização e as pessoas adicionadas no Grupo do Office 365, na lista de distribuição ou no grupo de segurança que são **Usuários Online com uma licença do Sistema de Telefonia** ou estão hospedados no local usando o Skype for Business Server 2015 ou o Lync Server 2013. Você pode adicionar vários Grupos do Office 365, listas de distribuição e grupos de segurança. <br/><br/> 

    > [!Caution]
    > Usuários locais de implantações do Lync Server 2010 não são listados quando alguém pesquisa o diretório usando a Discagem por Nome. 
***
![Número 2](../images/sfbcallout2.png)<br/>Ao usar **Excluir**, você tem duas opções:
*    **Nenhum** Esta opção indica que nenhum usuário Online será excluído da pesquisa de diretório. 
*    **Personalizado** Se usar essa opção, você poderá pesquisar um Grupo de Office 365, uma lista de distribuição ou grupo de segurança criado na sua organização e as pessoas adicionadas a este Grupo do Office 365, lista de distribuição ou grupos de segurança serão excluídas da pesquisa do diretório. Você pode adicionar vários Grupos do Office 365, listas de distribuição e grupos de segurança. <br/><br/> 

    > [!Caution]
    > Usuários locais de implantações do Lync Server 2010 não são listados quando alguém pesquisa o diretório usando a Discagem por Nome.          
   
> [!NOTE]
> Pode levar até 36 horas para um novo usuário ter seu nome listado no diretório quando alguém usar a Discagem por Nome com reconhecimento de fala. 
  
Depois de preencher todos os campos obrigatórios e configurar os menus e as opções de administração de chamadas, clique em **Salvar**.
  
## <a name="editing-and-testing-auto-attendants"></a>Editar e testar atendedores automáticos

Depois de salvar o atendedor automático, ele será listado na página **Atendedores automáticos**. Isso permitirá que você veja rapidamente algumas das opções configuradas, incluindo o nome, o número do telefone, o idioma e o status.
  
Se desejar fazer alterações em um atendedor automático, selecione-o e, no Painel de Ações, clique em **Editar**.
  
Você também pode fazer uma chamada de teste rapidamente para o atendedor automático usando o botão **Testar** no Painel de Ações.
  
## <a name="want-to-know-more"></a>Deseja saber mais?

Você também pode usar o Windows PowerShell para criar e configurar atendedores automáticos.
  
### <a name="auto-attendant-cmdlets"></a>Cmdlets de atendedores automáticos

Veja os cmdlets necessários para gerenciar um atendedor automático.
  
||| 
|---|---|
[New-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796493.aspx)                                                                      | [New-CsOrganizationalAutoAttendantPrompt](https://technet.microsoft.com/library/mt796484.aspx)                                                              |
| [Set-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796486.aspx)                                                                      | [New-CsOrganizationalAutoAttendantMenuOption](https://technet.microsoft.com/library/mt796485.aspx)                                                           |
| [Get-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796482.aspx)                                                                      | [Get-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/get-csorganizationalautoattendantholidays?view=skype-ps)       |
| [Remove-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796492.aspx)                                                                   | [New-CsOrganizationalAutoAttendantMenu](https://technet.microsoft.com/library/mt796488.aspx)                                                                  |
| [New- CsOnlineAudioFile](https://technet.microsoft.com/library/mt796479.aspx)                                                                                 | [New-CsOrganizationalAutoAttendantCallFlow](https://technet.microsoft.com/library/mt796489.aspx)                                                              |
| [Export-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps) | [New-CsOnlineTimeRange](https://technet.microsoft.com/library/mt796491.aspx)                                                                                  |
| [New-CsOnlineDateTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps)                                       | [New-CsOnlineSchedule](https://technet.microsoft.com/library/mt796490.aspx)                                                                                   |
| [Get-CsOrganizationalAutoAttendantSupportedTimeZone](https://technet.microsoft.com/library/mt796483.aspx)                                                     | [New-CsOrganizationalAutoAttendantCallHandlingAssociation](https://technet.microsoft.com/library/mt796487.aspx)                                               |
| [Get-CsOrganizationalAutoAttendantSupportedLanguage](https://technet.microsoft.com/library/mt796481.aspx)                                                     | [Import-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/import-csorganizationalautoattendantholidays?view=skype-ps) |
| [New-CsOrganizationalAutoAttendantCallableEntity](https://technet.microsoft.com/library/mt796480.aspx)                                                      |  |   |
   
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
    
  
 
