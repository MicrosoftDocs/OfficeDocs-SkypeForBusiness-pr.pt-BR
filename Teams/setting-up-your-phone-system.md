---
title: Configuração do Sistema de Telefonia na sua organização
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
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
description: 'Saiba como configurar o sistema telefônico (nuvem PBX) para sua organização. '
ms.openlocfilehash: 92d575a3219bcf2a99c48040b77b0eaa2463b25a
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2018
ms.locfileid: "25017683"
---
# <a name="setting-up-phone-system-in-your-organization"></a>Configuração do Sistema de Telefonia na sua organização

A seguir está um guia passo a passo para configurar o Sistema de Telefonia no Office 365. Links para informações detalhadas adicionais estão disponíveis no final de cada etapa.

## <a name="step-1-make-sure-that-phone-system-is-available-in-your-country-or-region"></a>Etapa 1: Certifique-se de que o Sistema de Telefonia está disponível em seu país ou região

1.  Primeiro, acesse [Disponibilidade de Audioconferência e Planos de Chamadas por país e região](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) e selecione seu país ou região na lista na parte superior da página. 
2.  Em **Sistema de Telefonia**, examine a lista de recursos e detalhes. 
3.  Se o Sistema de Telefonia estiver disponível, vá para a etapa 2. 

**Para saber mais sobre disponibilidade regional do Sistema de Telefonia e Audioconferência, consulte [Disponibilidade de Audioconferência e Planos de Chamada por país e região](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).**

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a>Etapa 2: Comprar e atribuir licenças do Sistema de Telefonia e Planos de Chamadas

Para atribuir uma licença de Sistema de Telefonia e Plano de Chamadas a um único usuário, as etapas são as mesmos da atribuição de licença do Office 365. Consulte [Atribuir Skype para licenças de negócios e equipes da Microsoft](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses). Se você desejar atribuir vários usuários de uma vez, consulte [Atribuir licenças do Skype for Business e do Microsoft Teams](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).

## <a name="step-3-get-phone-numbers-for-your-users"></a>Etapa 3: Obtenha números de telefone para seus usuários

Antes de você pode configurar os usuários em sua organização façam e recebam chamadas telefônicas, você deve obter números de telefone para eles.

Há três maneiras de obtenção de números para seus usuários:
- Obtenha novos números por meio do centro de administração do Skype for Business.
- Obtenha novos números que não estão disponíveis no centro de administração do Skype for Business.
- Porta ou transferir seus números de existentes do seu provedor de serviço atual ou a operadora de telefone para o Office 365.

Você deve usar a página **Adicionar novo usuário números** para ver, pesquisa, adquirir e reservar esses números. Você pode pesquisar por cidade, estado e país/região e digite o número dos números de telefone, que você precisará para seus usuários.

### <a name="get-new-user-phone-numbers"></a>Obtenha números de telefone do novo usuário 
 
![logotipo-sfb-30x30.png](media/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**

1. Entre no Office 365 com sua conta corporativa ou de estudante.

2. Navegue para o **Centro de administração do Office 365** > **Skype for Business**.
    
3. No painel de navegação esquerdo, acesse **Voz** > **Números de telefone**, clique em **Adicionar novo número** ![Adicionar botão](media/c224fbd0-f0f5-46ce-a1a7-73adf4540ef7.png) e depois clique em **Novos números de usuários**.
    
### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a>Obtenha novos números que não estão disponíveis no centro de administração do Skype for Business
  
Às vezes (dependendo do seu país/região) não será possível obter seus números de novos usando o Skype para o Centro de administração de negócios. Nesse caso, você precisará fazer o download de um formulário e enviá-la de volta para nós. Consulte [Gerenciar números de telefone da organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) para saber como solicitar novos números de usuário.   
  
### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>Fazer a portabilidade ou transferir os números de telefone de seu provedor de serviços ou de sua operadora de telefonia
  
- Se você precisar 999 ou menos números de telefone para seus usuários, você pode usar o Assistente de **Nova ordem de porta do número Local** do Skype para centro de administração de negócios. Siga as etapas encontradas em [números de telefone de transferência para o Office 365](transfer-phone-numbers-to-office-365.md) para transferir seus números de telefone sobre para Skype para negócios Online.
    
- Se você precisar mais do que 999 números de telefone de porta, consulte [gerenciar números de telefone para sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) para enviar uma solicitação de serviço de ordem de porta ou a ordem para obter todos esses números de telefone migrados para o Office 365. 

**Para obter informações detalhadas sobre como obter novos números de telefone ou transferir números existentes, consulte [Gerenciar números de telefone da sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).**

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>Etapa 4: Obtenha números de telefone do serviço (audioconferência, filas de chamadas, atendedores automáticos)

Além de obter números de telefone para os usuários do Office 365, você pode pesquisar e adquirir tarifas ou números de telefone gratuitos de serviços, como serviços de audioconferência (para pontes de conferência), atendedores automáticos e filas de chamada (também chamadas de números de serviço). Os números telefônicos de serviço têm uma capacidade de chamada simultânea maior do que números de usuários ou assinantes. Por exemplo, um número de serviço pode manipular 100s de chamadas simultaneamente, enquanto o número de telefone de um usuário pode manipular apenas algumas chamadas simultaneamente.

### <a name="get-new-service-numbers"></a>Obtenha novos números de serviço

![logotipo-sfb-30x30.png](media/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**


1. Entre no Office 365 com sua conta corporativa ou de estudante.

2. Navegue para o **Centro de administração do Office 365** > **Skype for Business**.

3. No painel de navegação esquerdo, vá para **voz** > **números de telefone** > **Adicionar novo número**e clique em **novos números de serviço**.

    > [!IMPORTANT]
    > Para você ver a opção de **voz** no painel de navegação esquerdo no Skype para centro de administração de negócios, primeiro você deve comprar uma licença de complemento de **Conferência de áudio** , uma licença de complemento de **Sistema telefônico** ou pelo menos uma **licença Enterprise E5**.

### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a>Obtenha novos números que não estão disponíveis no centro de administração do Skype for Business
  
Às vezes (dependendo do seu país/região) não será possível obter seus números de novos usando o Skype para o Centro de administração de negócios. Nesse caso, você precisará fazer o download de um formulário e enviá-la de volta para nós. Consulte [Gerenciar números de telefone da sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) para saber como solicitar novos números de usuário. 

### <a name="port-or-transfer-existing-service-numbers"></a>Fazer a portabilidade ou transfira números de serviço existentes

Se deseja transferir números de serviço do seu provedor de serviço ou operadora atuais, você precisa enviar manualmente um pedido de portabilidade para a Microsoft. Você precisa enviar pedidos de portabilidade individuais para cada tipo de número de serviço (pagos e gratuitos) que serão transferidos usando uma Carta de Autorização (LOA). Na Carta de Autorização (LOA), você deve selecionar o tipo de número de serviço correto. Ao contatar o suporte da Microsoft, não esqueça de especificar que você está transferindo um número de serviço (*e não um número de assinante ou de usuário*), ou a capacidade de chamadas simultâneas talvez não seja suficiente para lidar com grandes volumes de chamadas. Se você deseja transferir números de telefone ou fazer outras coisas com seus números, consulte [Gerenciar números de telefone da sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a>Etapa 5: Se você quiser configurar Planos de Chamadas

Se você seguiu as etapas acima, então já comprou e atribuiu um Sistema de Telefonia, licenças e um Plano de Chamadas (etapa 2), também já adquiriu números de telefone para seus usuários (etapa 3), portanto, seu Plano de Chamadas já está parcialmente configurado. Siga os três procedimentos abaixo para concluir a configuração.

### <a name="add-emergency-addresses-and-locations-for-your-organization"></a>Adicionar endereços de emergências e locais para sua organização

1. Na página de **voz** , escolha **locais de emergência** > **Adicionar novo endereço**.

2. No painel **Novo endereço**, insira um nome para seu endereço. Em seguida, preencha as caixas restantes.
    
     ![Quando você insere um novo endereça de emergência, o formato do nome da rua pode causar um erro.](media/dc1c5ef3-0554-4fb7-9ab1-5ea3ac9e5eb5.png)
  
    > [!TIP]
    > [!DICA] Para clientes ingleses, se o nome da rua for um número, inclua "st" ou "th" no fim, como mostrado na imagem acima.

3. Escolha **Validar**.

    Se necessário, você será solicitado a fazer correções no endereço.

    > [!CAUTION]
    > [!CUIDADO] Validar um endereço de rua ou civil envolve a certificação de que ele é legítimo e foi corretamente formatado. É possível que um endereço de emergência parcialmente correto, tais como se você digitado incorretamente o nome da cidade, talvez ainda passar validação. Mesmo que tenha sido escrito errado e aprovado na validação, a combinação do nome errado da cidade com outras partes corretas do endereço é suficiente para encaminhar a chamada para o centro de despacho de emergência apropriado.

    > [!TIP]
    > [!DICA] Se o endereço precisar ser corrigido para resposta a emergências, uma faixa verde será exibida para informar que o endereço foi atualizado.

4. Depois que o endereço for validado, escolha **Salvar**.

### <a name="assign-phone-numbers-and-emergency-addresses-to-users"></a>Atribuir números de telefone e endereços de emergência aos usuários

> [!TIP]
> [!DICA] Se você adicionar mais pessoas à sua empresa antes de realizar esta etapa, é possível que leve **várias horas** para que elas apareçam na página **Usuários de voz**. Há uma latência.

1. Na página **usuários de voz** , selecione as pessoas que você deseja atribuir um número de telefone e endereço de emergência para.

2. No painel Ação, clique em **Atribuir número**.

3. Na página **Atribuir número** , na lista **Selecione o número a ser atribuído** , selecione o número de telefone para o usuário.

4. Selecione um endereço de emergência, insira o nome da cidade na caixa e escolha **Pesquisar**.

    > [!IMPORTANT]
    > Se você estiver fora dos Estados Unidos, seus números já tem um endereço de emergência, mas você pode alterá-lo agora. Veja [Atribuir ou alterar o endereço de emergência de um usuário](/skypeforbusiness/what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user). 
  
5. Depois de atribuir o número de telefone e o endereço de emergência, clique em **Salvar**.

### <a name="tell-your-users-about-their-new-phone-numbers"></a>Informar os usuários sobre seus números de telefone de novo


Recomendamos o envio de emails ou o uso do método de comunicação preferido da sua empresa para avisar as pessoas sobre os novos números de telefone.

Aqui está como eles podem ver o número de telefone no app seus **Skype para negócios** :

1. Entrar no Skype for Business em sua área de trabalho.
    
2. Escolher **Configurações** > **Ferramentas** > **Opções**. 
    
     ![Para ver seu número de telefone, acesse Configurações > Ferramentas > Opções.](media/20637117-91d7-4a7e-9f06-7abc634a9211.png)
  
3. Em seguida, escolha **Telefones**. 
    
    ![A user can see their assign number in the Skype for Business app by choosing Settings > Tools > Options > Phone.](media/0128d667-2bf8-4165-b703-e9b78a15b63c.png)
 
No **Microsoft Teams**, os usuários podem ver o número de telefone clicando em **Chamadas** no painel de navegação à esquerda. O número de telefone é mostrado acima do teclado de discagem.

![Um usuário pode ver o número de telefone no Microsoft Teams clicando em Chamadas no painel de navegação à esquerda.](media/teams-phone-number.png)

**Para obter informações mais detalhadas sobre todas as etapas da configuração de um Plano de Chamadas consulte [Configurar Planos de Chamadas](set-up-calling-plans.md).**


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a>Etapa 6: Se você deseja configurar a Audioconferência

Às vezes, as pessoas em sua organização precisarão usar um telefone para ligar para uma reunião. Skype para Teams da Microsoft e de negócios incluir o recurso de conferência de áudio para apenas essa situação! As pessoas podem ligar para Skype para reuniões de negócios ou Microsoft Teams usando um telefone, em vez de usar o Skype para negócios ou Teams Microsoft app em um PC ou dispositivo móvel.

Você precisa configurar a conferência de áudio para as pessoas que pretende agendar ou liderança de reuniões. Os participantes da reunião não precisam de nenhuma licença atribuída ou configuração adicional.
  
Para as perguntas frequentes sobre Audioconferência, consulte [Perguntas comuns sobre Audioconferência](audio-conferencing-common-questions.md).
    
1. Se você adquiriu licenças complementares de **Audioconferência** e licenças Créditos de Comunicação, atribua-as também. Para obter instruções, consulte [Atribuir Skype para licenças de negócios e equipes da Microsoft](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).

    Decida sobre o seu provedor de serviços de audioconferência. Um provedor de serviços de audioconferência fornece uma ponte de audioconferência. A ponte de conferência define seus números de telefone de discagem, PINs e IDs de conferência para reuniões. Decida se prefere usar a Microsoft ou um provedor de serviços de audioconferência de terceiros:

    > [!NOTE]
    > Usuários do Microsoft Teams não podem usar um provedor de serviços de audioconferência de terceiros.

    - **Microsoft como provedor de serviços de audioconferência**: Se você quer a solução mais simples para audioconferência, escolha a Microsoft como seu provedor de serviços.
    
    - **Outros provedores de serviços de audioconferência**: Se você estiver em um país onde os serviços de audioconferência no Office 365 não estão disponíveis, a qualidade de serviço não é ótima devido à sua localização, ou se já tiver um contrato existente, escolha um provedor de serviços de audioconferência de terceiros. Para encontrar um provedor, acesse [Microsoft PinPoint](http://go.microsoft.com/fwlink/?LinkId=797530).
 
2.  Atribua o provedor de serviços de audioconferência às pessoas que agendam ou lideram reuniões. Consulte [Atribuir Microsoft como um provedor de serviços de audioconferência](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).

3. Configurar convites para reuniões. As etapas a seguir são opcionais, mas muitos administradores gostam de segui-las: 
  
    1. [Personalizar convites de reunião em Skype para negócios](/skypeforbusiness/set-up-skype-for-business-online/customize-meeting-invitations). Os números de discagem definidos para o usuário serão adicionados automaticamente aos convites da reunião enviados aos participantes. No entanto, você pode adicionar seus próprios links de ajuda e informações jurídicas, uma mensagem de texto e um pequeno gráfico da empresa.
    
    2. Defina os números de telefone de conferência de áudio para que estão incluídos na organizadores de reuniões convidam [em Skype para a empresa](/skypeforbusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites) ou [em equipes da Microsoft](set-the-phone-numbers-included-on-invites-in-teams.md). Esse é o número de telefone que serão exibidas na reunião programada pelo usuário.
    
    3. Definir idiomas de atendedor automático para conferência de áudio [no Skype para a empresa](/skypeforbusiness/audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing) ou [em equipes da Microsoft](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) que o atendedor automático de conferência de áudio usa para saudar um chamador quando eles discam para um número de telefone de conferência de áudio. Esta etapa só é válida se você estiver usando o Microsoft como provedor de áudio.
    
    4. Definir o tamanho do PIN para reuniões de conferência de áudio [em Skype para a empresa](/skypeforbusiness/audio-conferencing-in-office-365/set-the-pin-length-for-audio-conferencing-meetings) ou [em equipes da Microsoft](set-the-pin-length-for-audio-conferencing-meetings-in-teams.md).
    
    > [!NOTE]
    > Esse recurso ainda não disponível para clientes usando o Office 365 operado pela 21Vianet na China. Para saber mais, consulte [Saiba mais sobre o Office 365 operado pela 21Vianet](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE).

**Para obter mais informações sobre Audioconferência, consulte [Configurar Audioconferências](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing).**

## <a name="step-7-if-you-want-to-set-up-a-phone-system-call-queue"></a>Etapa 7: Se você deseja configurar uma fila de chamadas do Sistema de Telefonia

Telefonema de sistema filas incluem saudações que são usadas quando alguém chama um número de telefone para sua organização, a capacidade de colocar automaticamente as chamadas em espera e a capacidade de pesquisar para o próximo operador chamada disponíveis lidar com a chamada enquanto as pessoas que chamada está escutando a música em espera. Você pode criar uma fila de chamadas única ou múltiplas para a sua organização.

Antes de você poder criar e configurar as filas de chamada, será necessário receber ou transferir os números de serviço de chamada gratuita ou tarifada. Após obter os números de telefone de serviço gratuitos ou pagos, eles serão exibidos no **centro de administração do Skype for Business** > **Voz** > **Números de telefone**, e o **Tipo de número** listado será **Serviço - Gratuito**. Para obter seus números de serviço, consulte [Obter números de telefone de serviço para Skype for Business e Microsoft Teams](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers), ou se deseja transferir um número de serviço existente, consulte [Transferir números de telefone para o Office 365](transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Se você estiver fora dos Estados Unidos, você não pode usar o Skype para centro de administração de negócios para obter os números de serviço. Vá para [gerenciar números de telefone para sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) em vez disso, para ver como fazê-lo de fora dos Estados Unidos.

Para criar uma nova fila de chamadas, no **centro de administração do Skype for Business**, clique em **Roteamento de chamadas** > **Filas de chamadas**, depois clique em **Adicionar nova** e siga as instruções da **Etapa 3** do artigo  [Criar uma fila de chamadas para Sistema de Telefonia](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue#step-3---create-a-new-call-queue).

**Para obter mais detalhes sobre as filas de chamada, consulte [Criar uma fila de chamada do Sistema de Telefonia](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).**

## <a name="step-8-if-you-want-to-set-up-a-phone-system-auto-attendant"></a>Etapa 8: Se você quiser configurar um atendedor automático do Sistema de Telefonia

Atendedores automáticos permitem que as pessoas que ligam para sua organização e navegue para conectá-los ao departamento direita, chame a fila, pessoa ou o operador de um sistema de menus. Você pode criar um atendedor automático para sua organização usando o Skype para o Centro de administração de negócios.

Para criar um novo atendedor automático, no centro de administração do Skype for Business, clique em **Roteamento de chamadas** > **Atendedores automáticos**, depois clique em **Adicionar novo** e siga as instruções para cada página na **Etapa 2** do artigo [Configurar um atendedor automático para Sistema de Telefonia](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant#step-2---create-a-new-auto-attendant).

**Para obter mais detalhes sobre os atendedores automáticos de Sistema de Telefonia, consulte [Configurar um atendedor automático de Sistema de Telefonia](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant).**

## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>Etapa 9: Atribua números de telefone de serviço (audioconferência, filas de chamadas, atendedores automáticos)

Depois de seguir a **Etapa 4 acima** e conseguir seus números de serviço, você precisará atribuí-los a cada tipo de serviço que deseja. Por exemplo, se quiser um número de telefone de serviço dedicado (pago ou gratuito), você precisará atribuir o número à ponte de conferência.

- Para Audioconferências, você pode atribuir um número dedicado a uma ponte de Audioconferência acessando o **centro de administração do Office 365** > **Centros de administração** > **Skype for Business** > **Audioconferências** e clicando em ponte de conferência ou visualizando  [Alterar os números pagos ou gratuitos da sua ponte de Audioconferência](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

- Para Atendedores Automáticos, você pode atribuir um número dedicado acessando o **centro de administração do Office 365** > **Centros de administração** > **Skype for Business** > **Roteamento de chamadas** > **Atendedores automáticos** e clicando no atendedor automático. Na página **Geral**, o seu número de serviço atual será listado no menu suspenso **Número de telefone**. Para obter mais detalhes, consulte [Configurar um Atendedor Automático para Sistema de Telefonia](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant).

- Para Filas de Chamadas, você pode atribuir um número dedicado para uma fila de chamada acessando o **centro de administração do Office 365** > **Centros de administração** > **Skype for Business** > **Roteamento de chamadas** > **Filas de chamadas** e clicando na fila de chamadas. Na página **Geral**, o seu número de serviço atual será listado no menu suspenso**Número de telefone**. Para obter detalhes, consulte [Criar uma fila de chamadas do Sistema de Telefonia](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).

**Para obter informações detalhadas sobre como obter novos números de serviço e fazer a portabilidade de números de serviço existentes, consulte [Obter números de telefone de serviço](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers).**

## <a name="step-10-set-up-communications-credits-for-your-organization"></a>Etapa 10: Configurar os créditos de comunicações para sua organização

Você precisará configurar Créditos de Comunicação se quiser usar números gratuitos com o Skype for Business e o Microsoft Teams. Além disso, é recomendável que você configure créditos de comunicações para seus planos de chamada (doméstico ou internacional) e audioconferências usuários que precisam ter a capacidade de discar para **qualquer destino**. Muitos países/regiões são incluídos, mas alguns destinos não podem ser incluídos em suas assinaturas chamar planejar ou conferência de áudio. Se você não configurar créditos de comunicação de cobrança e atribuir uma licença **Créditos de comunicações** para seus usuários e executar check-out de minutos para sua organização (dependendo do seu plano de chamada ou conferência de áudio plano em seu país/região), esses usuários não será possível fazer chamadas ou discar a partir de reuniões de conferência de áudio. Você pode obter mais informações, incluindo recomendado, as quantidades de financiamento lendo [Cite Communications créditos?](what-are-communications-credits.md)
  
> [!NOTE]
> Para descobrir quanto isso custa, [consulte as taxas aqui](https://go.microsoft.com/fwlink/p/?LinkId=799523 ).

### <a name="to-set-up-communications-credits"></a>Configurar Créditos de Comunicação

1. Entre no Office 365 com sua conta corporativa ou de estudante.

2. No painel de navegação à esquerda no centro de administração do Office 365, acesse **Cobrança** > **Assinaturas** > **Complementos** > **Comprar complementos** e escolha **Créditos de Comunicação** > **Comprar agora**.

3. Na página de assinatura **Créditos de Comunicação**, preencha as informações e clique em **Avançar**.

4. Insira suas informações de pagamento e clique em **Fazer pedido**.
    >[!IMPORTANT]
    >Se você for um cliente de licenciamento por volume, você pode escolher seu número enterprise agreement para pagamento. Se você tiver vários números enterprise agreement, você pode escolher qual prefere usar para o pagamento. Você também poderá especificar um número de ordem de compra que será associado ao número do enterprise agreement (se aplicável).
    
**Para obter mais informações detalhadas sobre como configurar Créditos de Comunicação, consulte [Configurar créditos de Comunicação para a sua organização](set-up-communications-credits-for-your-organization.md).**
  
### <a name="assign-a-communications-credits-license-to-users"></a>Atribuir uma licença de Créditos de Comunicação aos usuários

1. Entre no Office 365 com sua conta corporativa ou de estudante.

2. No painel de navegação à esquerda do Centro de administração do Office 365, vá para **usuários** > **usuários ativos**e selecione um ou mais usuários da lista.

3. No painel Ação em **Licenças de**, clique em **Editar**.

4. Na página **licenças do produto** , alternar **Créditos de comunicações** para **em** para atribuir essa licença e clique em **Salvar**.

    > [!NOTE]
    > Mesmo se você tiver usuários que receberem uma licença **Enterprise E5** , ainda é recomendado que você faça isso.

**Para saber mais sobre como atribuir licenças Créditos de Comunicação, consulte [Configurar Créditos de Comunicação para sua organização](set-up-communications-credits-for-your-organization.md).**

## <a name="related-topics"></a>Tópicos relacionados
[Veja aqui o que é fornecido com o Sistema de Telefonia no Office 365](here-s-what-you-get-with-phone-system.md)

[Obtendo números de telefone de serviço do Skype for Business e do Microsoft Teams](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers)

[Disponibilidade da Audioconferência e dos Planos de Chamadas por país e região](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    
  
 
