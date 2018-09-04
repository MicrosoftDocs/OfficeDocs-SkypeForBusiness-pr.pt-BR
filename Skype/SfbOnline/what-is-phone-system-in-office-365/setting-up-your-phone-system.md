---
title: Configuração do Sistema de Telefonia na sua organização
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.topic: article
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
description: 'Saiba como configurar o Sistema de Telefonia (PBX na nuvem) para sua organização. '
ms.openlocfilehash: 2566bfcef892767f89afb28643deb91942596e76
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23244626"
---
# <a name="setting-up-phone-system-in-your-organization"></a>Configuração do Sistema de Telefonia na sua organização

A seguir está um guia passo a passo para configurar o Sistema de Telefonia no Office 365. Links para informações detalhadas adicionais estão disponíveis no final de cada etapa.

## <a name="step-1-make-sure-that-phone-system-is-available-in-your-country-or-region"></a>Etapa 1: Certifique-se de que o Sistema de Telefonia está disponível em seu país ou região

1.  Primeiro, acesse [Disponibilidade de Audioconferência e Planos de Chamadas por país e região](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) e selecione seu país ou região na lista na parte superior da página.
2.  Em **Sistema de Telefonia**, examine a lista de recursos e detalhes.
3.  Se o Sistema de Telefonia estiver disponível, vá para a etapa 2.

**Para saber mais sobre disponibilidade regional do Sistema de Telefonia e Audioconferência, consulte [Disponibilidade de Audioconferência e Planos de Chamada por país e região](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).**

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a>Etapa 2: Comprar e atribuir licenças do Sistema de Telefonia e Planos de Chamadas

Para atribuir uma licença de Sistema de Telefonia e Plano de Chamadas a um único usuário, as etapas são as mesmos da atribuição de licença do Office 365. Veja [Atribuir licenças do Skype for Business e do Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Se você desejar atribuir vários usuários de uma vez, consulte [Atribuir licenças do Skype for Business e do Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

## <a name="step-3-get-phone-numbers-for-your-users"></a>Etapa 3: Obtenha números de telefone para seus usuários

Antes de você pode configurar os usuários da sua organização para fazer e receber chamadas telefônicas, você deve obter números de telefone para eles.

Você pode fazer isso de três formas:
- Obtenha novos números por meio do centro de administração do Skype for Business.
- Obtenha novos números que não estão disponíveis no centro de administração do Skype for Business.
- Faça a portabilidade ou transfira os números existentes do seu provedor de serviços ou operadora de telefonia atual para o Office 365.

Você precisa usar a página **Adicionar novos números de usuários** para ver, pesquisar, adquirir e reservar esses números. Você pode pesquisar por País/Região, Estado e Cidade e, depois, digitar a quantidade de números de telefone necessários para os usuários.

### <a name="get-new-user-phone-numbers"></a>Obter números de telefone novos para usuários

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Usar o centro de administração do Skype for Business**


1. Entre no Office 365 com sua conta corporativa ou de estudante.

2. Vá para o **Centro de administração do Office 365** > **Skype for Business**.

3. No painel de navegação esquerdo, acesse **Voz** > **Números de telefone**, clique em **Adicionar novo número** ![Adicionar botão](../images/c224fbd0-f0f5-46ce-a1a7-73adf4540ef7.png) e depois clique em **Novos números de usuários**.

### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a>Obtenha novos números que não estão disponíveis no centro de administração do Skype for Business

Às vezes (dependendo do seu país/região) não será possível obter seus números novos usando o centro de administração do Skype for Business. Nesse caso, você precisará fazer o download de um formulário e enviá-lo de volta para nós. Consulte [Gerenciar números de telefone da organização](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) para saber como solicitar novos números de usuário.

### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>Fazer a portabilidade ou transferir os números de telefone do seu provedor de serviços ou operadora de telefonia

- Se precisar de 999 ou menos números telefone para seus usuários, você pode usar o assistente **Novo Pedido de Portabilidade de Número Local** no centro de administração do Skype for Business. Siga as etapas encontradas em [Transferir números de telefone para o Office 365](..//what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md) para transferir seus números para o Skype for Business Online.

- Se você precisar fazer a portabilidade de mais de 999 números de telefone, consulte [Gerenciar números de telefone da sua organização](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) para enviar um pedido de portabilidade para que todos esses números de telefone sejam transferidos para o Office 365.

**Para obter informações detalhadas sobre como obter novos números de telefone ou transferir números existentes, consulte [Gerenciar números de telefone da sua organização](../what-are-calling-plans-in-office-365\manage-phone-numbers-for-your-organization\manage-phone-numbers-for-your-organization.md).**

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>Etapa 4: Obtenha números de telefone do serviço (audioconferência, filas de chamadas, atendedores automáticos)

Além de obter números de telefone para os usuários do Office 365, você pode pesquisar e adquirir tarifas ou números de telefone gratuitos ou pagos para serviços como audioconferência (para pontes de conferência), atendedores automáticos e filas de chamadas (também chamados de números de serviço). Os números de telefone de serviço têm uma capacidade maior de chamadas simultâneas do que os números de usuários ou assinantes. Por exemplo, um número de serviço pode lidar com centenas de chamadas simultaneamente, enquanto um número de usuário só consegue lidar com algumas.

### <a name="get-new-service-numbers"></a>Obtenha novos números de serviço

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Usar o centro de administração do Skype for Business**


1. Entre no Office 365 com sua conta corporativa ou de estudante.

2. Vá para o **Centro de administração do Office 365** > **Skype for Business**.

3. No painel de navegação à esquerda, acesse **Voz** > **Números de telefone** > **Adicionar novo número** e depois clique em**Novos números de serviço**.

    > [!IMPORTANT]
    > Para ver a opção **Voz** no painel de navegação à esquerda no centro de administração do Skype for Business, você deve comprar pelo menos uma **licença Enterprise E5**, uma licença complementar de **Sistema Telefônico** ou uma licença complementar de **Audioconferência**.

### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a>Obtenha novos números que não estão disponíveis no centro de administração do Skype for Business

Às vezes (dependendo do seu país/região) não será possível obter seus números novos usando o centro de administração do Skype for Business. Nesse caso, você precisará fazer o download de um formulário e enviá-lo de volta para nós. Consulte [Gerenciar números de telefone da sua organização](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) para saber como solicitar novos números de usuário.

### <a name="port-or-transfer-existing-service-numbers"></a>Fazer a portabilidade ou transferir números de serviço existentes

Se deseja transferir números de serviço do seu provedor de serviço ou operadora atuais, você precisa enviar manualmente um pedido de portabilidade para a Microsoft. Você precisa enviar pedidos de portabilidade individuais para cada tipo de número de serviço (pagos e gratuitos) que serão transferidos usando uma Carta de Autorização (LOA). Na Carta de Autorização (LOA), você deve selecionar o tipo de número de serviço correto. Ao contatar o suporte da Microsoft, não esqueça de especificar que você está transferindo um número de serviço (*e não um número de assinante ou de usuário*), ou a capacidade de chamadas simultâneas talvez não seja suficiente para lidar com grandes volumes de chamadas. Se você deseja transferir números de telefone ou fazer outras coisas com seus números, consulte [Gerenciar números de telefone da sua organização](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a>Etapa 5: Se você quiser configurar Planos de Chamadas

Se você seguiu as etapas acima, então já comprou e atribuiu um Sistema de Telefonia, licenças e um Plano de Chamadas (etapa 2), também já adquiriu números de telefone para seus usuários (etapa 3), portanto, seu Plano de Chamadas já está parcialmente configurado. Siga os três procedimentos abaixo para concluir a configuração.

### <a name="add-emergency-addresses-and-locations-for-your-organization"></a>Adicionar endereços e locais de emergência para a sua organização

1. Na página **Voz**, escolha **Locais de emergência** > **Adicionar novo endereço**.

2. No painel **Novo endereço**, insira um nome para seu endereço. Em seguida, preencha as caixas restantes.

     ![Quando você insere um novo endereça de emergência, o formato do nome da rua pode causar um erro.](../images/dc1c5ef3-0554-4fb7-9ab1-5ea3ac9e5eb5.png)

    > [!TIP]
    > [!DICA] Para clientes ingleses, se o nome da rua for um número, inclua "st" ou "th" no fim, como mostrado na imagem acima.

3. Escolha **Validar**.

    Se necessário, você será solicitado a fazer correções no endereço.

    > [!CAUTION]
    > Validar um endereço civil ou de rua envolve verificar se ele é legítimo e se está no formato correto. É possível que um endereço de emergência parcialmente correto (como com erros de digitação) passe na validação. Mesmo que tenha sido escrito errado e aprovado na validação, a combinação do nome errado da cidade com outras partes corretas do endereço é suficiente para encaminhar a chamada para o centro de despacho de emergência apropriado.

    > [!TIP]
    > [!DICA] Se o endereço precisar ser corrigido para resposta a emergências, uma faixa verde será exibida para informar que o endereço foi atualizado.

4. Depois que o endereço for validado, escolha **Salvar**.

### <a name="assign-phone-numbers-and-emergency-addresses-to-users"></a>Atribuir números de telefone e endereços de emergência aos usuários

> [!TIP]
> [!DICA] Se você adicionar mais pessoas à sua empresa antes de realizar esta etapa, é possível que leve **várias horas** para que elas apareçam na página **Usuários de voz**. Há uma latência.

1. Na página **Usuários de voz**, escolha as pessoas às quais deseja atribuir um número de telefone e um endereço de emergência.

2. No painel Ação, clique em **Atribuir número**.

3. Na página **Atribuir número**, na lista **Selecionar um número para atribuir**, selecione o número de telefone para o usuário.

4. Para selecionar um endereço de emergência, insira o nome da cidade na caixa e escolha **Pesquisar**.

    > [!IMPORTANT]
    > Se você está fora dos Estados Unidos, seus números já têm um endereço de emergência, mas agora você pode alterá-lo. Veja [Atribuir ou alterar o endereço de emergência de um usuário](../what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user.md).

5. Depois de atribuir o número de telefone e o endereço de emergência, clique em **Salvar**.

### <a name="tell-your-users-about-their-new-phone-numbers"></a>Informe os usuários sobre seus novos números de telefone


Recomendamos o envio de e-mails ou outro método de comunicação preferido pela empresa para avisar as pessoas sobre os novos números de telefone.

Eles podem visualizar esse número de telefone no aplicativo do **Skype for Business** assim:

1. Entrar no Skype for Business na área de trabalho.

2. Escolher **Configurações** > **Ferramentas** > **Opções**.

     ![Para ver seu número de telefone, acesse Configurações > Ferramentas > Opções.](../images/20637117-91d7-4a7e-9f06-7abc634a9211.png)

3. Em seguida, escolha **Telefones**.

    ![Um usuário pode ver seu número de telefone atribuído no aplicativo Skype for Business acessando Configurações > Ferramentas > Opções > Telefone.](../images/0128d667-2bf8-4165-b703-e9b78a15b63c.png)

No **Microsoft Teams**, os usuários podem ver o número de telefone clicando em **Chamadas** no painel de navegação à esquerda. O número de telefone é mostrado acima do teclado de discagem.

![Um usuário pode ver o número de telefone no Microsoft Teams clicando em Chamadas no painel de navegação à esquerda.](../images/teams-phone-number.png)

**Para obter informações mais detalhadas sobre todas as etapas da configuração de um Plano de Chamadas consulte [Configurar Planos de Chamadas](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).**


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a>Etapa 6: Se você deseja configurar a Audioconferência

Às vezes, as pessoas da sua organização precisarão usar um telefone para acessar uma reunião. O Skype for Business e o Microsoft Teams incluem o recurso de Audioconferência exatamente para essa situação! As pessoas podem acessar reuniões do Skype for Business ou Microsoft Teams usando um telefone, em vez do aplicativo Skype for Business ou Microsoft Teams em um PC ou dispositivo móvel.

Você só precisa configurar a Audioconferência para as pessoas que costumam agendar ou liderar reuniões. Os participantes da reunião não precisam de nenhuma licença atribuída ou configuração adicional.

Para as perguntas frequentes sobre Audioconferência, consulte [Perguntas comuns sobre Audioconferência](../audio-conferencing-in-office-365/audio-conferencing-common-questions.md).

1. Se você adquiriu licenças complementares de **Audioconferência** e licenças Créditos de Comunicação, atribua-as também. Para instruções, veja [Atribuir licenças do Skype for Business e do Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

    Decida sobre o seu provedor de serviços de audioconferência. Um provedor de serviços de audioconferência fornece uma ponte de audioconferência. A ponte de conferência define os números de telefone de acesso, PINs e IDs de conferência para reuniões. Decida se prefere usar a Microsoft ou um provedor de serviços de audioconferência de terceiros:

    > [!NOTE]
    > Usuários do Microsoft Teams não podem usar um provedor de serviços de audioconferência de terceiros.

    - **Microsoft como provedor de serviços de audioconferência**: Se você quer a solução mais simples para audioconferência, escolha a Microsoft como seu provedor de serviços.

    - **Outros provedores de serviços de audioconferência**: Se você estiver em um país onde os serviços de audioconferência no Office 365 não estão disponíveis, a qualidade de serviço não é ótima devido à sua localização, ou se já tiver um contrato existente, escolha um provedor de serviços de audioconferência de terceiros. Para encontrar um provedor, acesse [Microsoft PinPoint](https://go.microsoft.com/fwlink/?LinkId=797530).

2.  Atribua o provedor de serviços de audioconferência às pessoas que agendam ou lideram reuniões. Veja [Atribuir a Microsoft como provedor de audioconferência](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).

3. Configurar convites para reuniões. As etapas a seguir são opcionais, mas muitos administradores gostam de segui-las:

    1. [Personalizar convites de reunião](../set-up-skype-for-business-online/customize-meeting-invitations.md). Os números de acesso definidos para o usuário serão adicionados automaticamente aos convites da reunião enviados aos participantes. No entanto, você pode adicionar seus próprios links de ajuda e informações jurídicas, uma mensagem de texto e um pequeno gráfico da empresa.

    2. [Definir os números de telefone de audioconferência para organizadores da reunião incluídos nos convites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md). Esse é o número de telefone que aparecerá na reunião agendada pelo usuário.

    3. [Definir os idiomas do atendedor automático da Audioconferência](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) usados para cumprimentar quem liga para o número de acesso da Audioconferência. Esta etapa só é válida se você estiver usando o Microsoft como provedor de áudio.

    4. [Definir o tamanho do PIN para reuniões de Audioconferência](../audio-conferencing-in-office-365/set-the-pin-length-for-audio-conferencing-meetings.md).

    > [!NOTE]
    > Esse recurso ainda não disponível para clientes usando o Office 365 operado pela 21Vianet na China. Para saber mais, consulte [Saiba mais sobre o Office 365 operado pela 21Vianet](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE).

**Para obter mais informações sobre Audioconferência, consulte [Configurar Audioconferências](../audio-conferencing-in-office-365/set-up-audio-conferencing.md).**

## <a name="step-7-if-you-want-to-set-up-a-phone-system-call-queue"></a>Etapa 7: Se você deseja configurar uma fila de chamadas do Sistema de Telefonia

Filas de chamadas do Sistema de Telefonia incluem saudações usadas quando alguém liga para um número de telefone da sua organização, a capacidade de automaticamente colocar chamadas em espera e pesquisar o próximo operador disponível para atender a chamada enquanto a pessoa que ligou escuta a música de espera. Você pode criar uma fila de chamadas única ou múltiplas para a sua organização.

Antes de você poder criar e configurar as filas de chamada, será necessário receber ou transferir os números de serviço de chamada gratuita ou tarifada. Após obter os números de telefone de serviço gratuitos ou pagos, eles serão exibidos no **centro de administração do Skype for Business** > **Voz** > **Números de telefone**, e o **Tipo de número listado** será **Serviço - Gratuito**. Para obter seus números de serviço, consulte [Obter números de telefone de serviço para Skype for Business e Microsoft Teams](getting-service-phone-numbers.md), ou se deseja transferir um número de serviço existente, consulte [Transferir números de telefone para o Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).

> [!NOTE]
> Se você estiver fora dos Estados Unidos, não será possível usar o centro de administração do Skype for Business para obter os números de serviço. Acesse [Gerenciar números de telefone da sua organização](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) para ver como fazer isso fora dos Estados Unidos.

Para criar uma nova fila de chamadas, no **centro de administração do Skype for Business**, clique em **Roteamento de chamadas** > **Filas de chamadas**, depois clique em **Adicionar nova** e siga as instruções da **Etapa 3** do artigo  [Criar uma fila de chamadas para Sistema de Telefonia]( create-a-phone-system-call-queue.md#step-3---create-a-new-call-queue).

**Para obter mais detalhes sobre as filas de chamada, consulte [Criar uma fila de chamada do Sistema de Telefonia](create-a-phone-system-call-queue.md).**

## <a name="step-8-if-you-want-to-set-up-a-phone-system-auto-attendant"></a>Etapa 8: Se você quiser configurar um atendedor automático do Sistema de Telefonia

Os atendedores automáticos direcionam as pessoas que ligam para a sua organização, navegando um sistema de menus para direcioná-las ao departamento, fila de chamadas, pessoa ou operador certo. Você pode criar um atendedor automático para sua organização usando o centro de administração do Skype for Business.

Para criar um novo atendedor automático, no centro de administração do Skype for Business, clique em **Roteamento de chamadas** > **Atendedores automáticos**, depois clique em **Adicionar novo** e siga as instruções para cada página na **Etapa 2** do artigo [Configurar um atendedor automático para Sistema de Telefonia](set-up-a-phone-system-auto-attendant.md#step-2---create-a-new-auto-attendant).

**Para obter mais detalhes sobre os atendedores automáticos de Sistema de Telefonia, consulte [Configurar um atendedor automático de Sistema de Telefonia](set-up-a-phone-system-auto-attendant.md).**

## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>Etapa 9: Atribua números de telefone de serviço (audioconferência, filas de chamadas, atendedores automáticos)

Depois de seguir a **Etapa 4 acima** e conseguir seus números de serviço, você precisará atribuí-los a cada tipo de serviço que deseja. Por exemplo, se quiser um número de telefone de serviço dedicado (pago ou gratuito), você precisará atribuir o número à ponte de conferência.

- Para Audioconferências, você pode atribuir um número dedicado a uma ponte de Audioconferência acessando o **centro de administração do Office 365** > **Centros de administração** > **Skype for Business** > **Audioconferências** e clicando em ponte de conferência ou visualizando  [Alterar os números pagos ou gratuitos da sua ponte de Audioconferência](../audio-conferencing-in-office-365/change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

- Para Atendedores Automáticos, você pode atribuir um número dedicado acessando o **centro de administração do Office 365** > **Centros de administração** > **Skype for Business** > **Roteamento de chamadas** > **Atendedores automáticos** e clicando no atendedor automático. Na página **Geral**, o seu número de serviço atual será listado no menu suspenso **Número de telefone**. Para obter mais detalhes, consulte [Configurar um Atendedor Automático para Sistema de Telefonia](set-up-a-phone-system-auto-attendant.md).

- Para Filas de Chamadas, você pode atribuir um número dedicado para uma fila de chamada acessando o **centro de administração do Office 365** > **Centros de administração** > **Skype for Business** > **Roteamento de chamadas** > **Filas de chamadas** e clicando na fila de chamadas. Na página **Geral**, o seu número de serviço atual será listado no menu suspenso**Número de telefone**. Para obter detalhes, consulte [Criar uma fila de chamadas do Sistema de Telefonia](create-a-phone-system-call-queue.md).

**Para obter informações detalhadas sobre como obter novos números de serviço e fazer a portabilidade de números de serviço existentes, consulte [Obter números de telefone de serviço](getting-service-phone-numbers.md).**

## <a name="step-10-set-up-communications-credits-for-your-organization"></a>Etapa 10: Configurar Créditos de Comunicação para a sua organização

Você precisará configurar Créditos de Comunicação se quiser usar números gratuitos com o Skype for Business e o Microsoft Teams. Além disso, é recomendável que você configure Créditos de Comunicação para seus Planos de Chamadas (doméstico ou internacional) e usuários de Audioconferências que precisam poder ligar para **qualquer número externo**. Muitos países/regiões estão incluídos, mas alguns destinos podem não fazer parte das suas assinaturas de Plano de Chamadas ou Audioconferência. Se você não configurar os dados de cobrança dos Créditos de Comunicação e atribuir uma licença de **Créditos de Comunicação** para seus usuários, e os minutos da sua organização acabarem (dependendo do Plano de Chamadas ou de Audioconferência do seu país/região), esses usuários conseguirão fazer chamadas ou discar a partir de reuniões de Audioconferência. Você encontrará mais informações, incluindo valores recomendados, em [O que são Créditos de Comunicação?](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md)

> [!NOTE]
> Para descobrir quanto isso custa, [consulte as taxas aqui](https://go.microsoft.com/fwlink/p/?LinkId=799523 ).

### <a name="to-set-up-communications-credits"></a>Configurar Créditos de Comunicação

1. Entre no Office 365 com sua conta corporativa ou de estudante.

2. No painel de navegação à esquerda no centro de administração do Office 365, acesse **Cobrança** > **Assinaturas** > **Complementos** > **Comprar complementos** e escolha **Créditos de Comunicação** > **Comprar agora**.

3. Na página de assinatura **Créditos de Comunicação**, preencha as informações e clique em **Avançar**.

4. Insira suas informações de pagamento e clique em **Fazer pedido**.
    >[!IMPORTANT]
    >Se você for um cliente de licenciamento por volume, você pode escolher seu número enterprise agreement para pagamento. Se você tiver vários números enterprise agreement, você pode escolher qual prefere usar para o pagamento. Você também poderá especificar um número de ordem de compra que será associado ao número do enterprise agreement (se aplicável).

**Para obter mais informações detalhadas sobre como configurar Créditos de Comunicação, consulte [Configurar créditos de Comunicação para a sua organização](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md).**

### <a name="assign-a-communications-credits-license-to-users"></a>Atribuir uma licença de Créditos de Comunicação aos usuários

1. Entre no Office 365 com sua conta corporativa ou de estudante.

2. Na barra de navegação à esquerda do centro de administração do Office 365, acesse **Usuários** > **Usuários ativos** e selecione os usuários na lista.

3. No painel Ação em **Licenças de produtos**, clique em **Editar**.

4. Na página **Licenças de produtos** , alterne os **Créditos de Comunicação** para **Habilitado** para atribuir essa licença e clique em **Salvar**.

    > [!NOTE]
    > Mesmo que haja usuários aos quais foi atribuída a licença **Enterprise E5**, ainda é recomendável fazer isso.

**Para saber mais sobre como atribuir licenças Créditos de Comunicação, consulte [Configurar Créditos de Comunicação para sua organização](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md).**

## <a name="related-topics"></a>Tópicos relacionados
[Veja aqui o que é fornecido com o Sistema de Telefonia no Office 365](here-s-what-you-get-with-phone-system.md)

[Obtendo números de telefone de serviço do Skype for Business e do Microsoft Teams](getting-service-phone-numbers.md)

[Disponibilidade da Audioconferência e dos Planos de Chamadas por país e região](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)


