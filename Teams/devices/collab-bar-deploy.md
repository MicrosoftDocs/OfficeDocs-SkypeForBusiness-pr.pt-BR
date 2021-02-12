---
title: Implantar barras de colaboração para o Microsoft Teams
ms.author: mitressl
author: flinchbot
manager: serdars
audience: ITPro
ms.reviewer: payurevi
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Leia este artigo para saber mais sobre como implantar barras de colaboração para o Microsoft Teams.
ms.openlocfilehash: 41eb3335eef78f1da2c64b1df65443ba93d40159
ms.sourcegitcommit: b255db7ef816d1884c9c71af86a901bd83a1d9ab
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962902"
---
# <a name="deploy-collaboration-bars-for-microsoft-teams"></a>Implantar barras de colaboração para o Microsoft Teams

A implantação de barras de colaboração para o Microsoft Teams pode ser dividida nas seguintes fases:

- **Preparação do site** Confirme se seus locais de implantação (salas) atendem aos requisitos de implantação.
- **Preparação do serviço** Crie contas de recursos e atribua-as aos dispositivos ( consulte Criar uma conta de recurso usando o Centro de administração [do Microsoft 365).](resource-account-ui.md) Embora seja recomendável usar uma licença de sala dedicada, uma conta de usuário final devidamente licenciada também pode entrar em barras de colaboração.
- **Configuração e implantação** Configurar barras de colaboração em salas e conectar os dispositivos periféricos necessários (consulte a documentação do fabricante para suas barras de colaboração).

Para gerenciar barras de colaboração, você precisa ser um administrador global, administrador do Serviço do Teams ou administrador de Dispositivo do Teams. Para obter mais informações sobre funções de administrador, [consulte Usar funções de administrador do Microsoft Teams para gerenciar o Teams.](../using-admin-roles.md)

## <a name="site-readiness"></a>Preparação do site

Enquanto os dispositivos ordenados estão sendo entregues à sua organização, trabalhe com sua rede, instalações e equipes audiovisual para garantir que os requisitos de implantação sejam atendidos e que cada site e sala esteja pronto em termos de energia, rede e exibição.

Nossas recomendações para sites de barra de colaboração são:

- Salas com até 4 pessoas
- Contas de recursos dedicadas
- Telas habilitadas para toque
- Cabeamento Ethernet
- QoS (Qualidade de Serviço) habilitada na rede para mídia do Microsoft Teams

Para considerações sobre a instalação física, consulte a documentação do fabricante e, se você tiver uma, aproveite a experiência da sua equipe audiovisual antes de instalar e montar telas e executar o cabeamento.

> [!TIP]
> Certifique-se de conferir Preparar sua rede para [o Teams](../prepare-network.md) para planejamento de largura de banda e avaliação da adequação da rede ao tráfego em tempo real.
>
> Não recomendamos a colocação de servidores proxy entre dispositivos Teams e a Internet. Para saber mais sobre servidores proxy e o Teams, confira [os servidores Proxy do Teams.](../proxy-servers-for-skype-for-business-online.md)

|    |     |
|-----------|------------|
| ![Um ícone representando pontos de decisão](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Confirme se seus sites atendem aos requisitos de preparação do site para barras de colaboração do Microsoft Teams.</li><li>Confirme que você forneceu largura de banda suficiente para cada site.</li></ul>|
| ![Um ícone representando as próximas etapas](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Comece a planejar a implantação e a configuração da barra de colaboração.</li></ul>|

## <a name="service-readiness"></a>Prontidão de serviço

Antes de implantar suas barras de colaboração, você precisa decidir se elas usarão contas de recurso do Microsoft 365, contas de usuário final ou uma combinação de ambos. As contas de recursos do Microsoft 365 são caixas de correio e contas do Teams dedicadas a recursos específicos, como uma sala, projetor e assim por diante. Essas contas de recurso podem responder automaticamente a convites de reunião usando regras definidas quando elas são criadas. A menos que uma barra de colaboração seja dedicada a um indivíduo específico para seu uso particular, recomendamos configurar uma conta de recurso do Microsoft 365 para ela.

### <a name="using-a-resource-account"></a>Usando uma conta de recurso

Se você decidir configurar uma conta de recurso do Microsoft 365, precisará comprar uma licença de Sala de Reunião para ela. A licença da Sala de Reunião inclui uma caixa de correio de recurso que permite que as pessoas em sua organização reservem a sala de reunião por meio do Outlook ou do Teams. A licença também permite vídeo, audioconferência e compartilhamento de tela entre os participantes da reunião.

Se você precisar receber ou fazer chamadas de um número de telefone externo, talvez precise de um Plano de Chamada ou de uma licença de complemento do Microsoft 365 Business [Voice.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing?tabs=small-business) Se você tiver o Roteamento Direto habilitado em sua organização, você só precisará da SKU da Sala de Reunião.

Ao criar uma conta de recurso, você pode optar por permitir que a conta aceite ou rebaixe automaticamente solicitações de reunião, permita reuniões recorrentes, especifique até que ponto as pessoas podem reservar o recurso e assim por diante.

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

Para obter mais informações sobre barras de colaboração para contas de recursos do Microsoft 365, consulte Criar uma conta de recurso usando o Centro de administração [do Microsoft 365.](resource-account-ui.md)

|    |     |
|-----------|------------|
| ![Um ícone representando pontos de decisão](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida se deseja fazer ou receber chamadas telefônicas externas e identificar requisitos de licenciamento para suas contas de recursos.</li></ul>|
| ![Um ícone representando as próximas etapas](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Preparar contas de recursos.</li></ul>|

## <a name="configuration-and-deployment"></a>Configuração e implantação

O planejamento de configuração e implantação abrange as seguintes áreas principais:

- Provisionamento de conta de recurso
- Implantação de dispositivo
- Barras de colaboração para configuração de aplicativo e dispositivo periférico do Microsoft Teams
-  Testes
- Gerenciamento de ativos

### <a name="account-provisioning"></a>Provisionamento de conta

Se você planeja usar contas de recursos do Microsoft 365 para permitir que os usuários reservem barras de colaboração, siga as instruções em Criar uma conta de recurso usando o Centro de administração do [Microsoft 365](resource-account-ui.md) para criar uma conta de recurso do Microsoft 365 para cada barra de colaboração que precise de uma. Também é aqui que você precisará adicionar uma licença de Sala de Reunião à conta do recurso e, se quiser fazer ou receber chamadas para ou de números de telefone externos, uma licença do Plano de Chamada ou do Business Voice se sua organização não estiver usando Roteamento Direto.

Se você quiser atribuir barras de colaboração a usuários individuais para seu uso particular, não será necessário configurar nenhuma conta adicional. Os usuários podem entrar em barras de colaboração usando suas contas pessoais.

> [!TIP]
> Faça com que os nomes de exibição das suas contas de recursos do Microsoft 365 descritivos e fáceis de entender. Esses são os nomes que os usuários verão ao pesquisar e adicionar barras de colaboração do Microsoft Teams às reuniões. Você poderia usar uma convenção como Nome da Sala de *Site*(Capacidade Máxima da Sala), portanto, Curie, uma sala de reunião de 4 pessoas em Londres, pode ter o nome de exibição - LON-CURIE(4).

|    |     |
|-----------|------------|
| ![Um ícone representando pontos de decisão](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida a convenção de nomenplicação para suas contas de recursos dedicadas.</li><li>Decida se você criará contas individuais ou usará scripts de provisionamento em massa.</li></ul>|
| ![Um ícone representando as próximas etapas](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Comece a planejar a implantação do dispositivo.</li></ul>|

### <a name="device-deployment"></a>Implantação de dispositivo

Em seguida, você precisa criar seu plano para entregar os dispositivos e os dispositivos periféricos atribuídos a suas salas e, em seguida, prosseguir com a instalação e a configuração.

|    |     |
|-----------|------------|
| ![Um ícone representando pontos de decisão](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida quem gerenciará a implantação local por site.</li><li> Identifique os recursos que instalarão as barras de colaboração do Microsoft Teams no local e realizará a configuração e os testes.</li></ul>|
| ![Um ícone representando as próximas etapas](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Inicie o teste do dispositivo.</li></ul>|

### <a name="testing"></a> Testes

Depois que as barras de colaboração do Microsoft Teams foram implantadas, você deve testá-las. Entre no dispositivo e verifique se os recursos esperados estão funcionando no dispositivo implantado. É altamente recomendável que você verifique se  os dispositivos  estão aparecendo na seção Barras de colaboração na guia Dispositivos do Centro de administração do Microsoft Teams. Também é importante que você faça várias chamadas de teste e reuniões para verificar a qualidade e o desempenho.

Recomendamos que, como parte da adoção geral do Microsoft Teams, configure a criação de arquivos para o Painel de Qualidade de Chamada (CQD), monitore tendências de qualidade e participe do processo de Revisão de Qualidade da Experiência. Para obter mais informações, consulte o [Guia de Revisão de Qualidade da Experiência.](https://aka.ms/qerguide)

### <a name="asset-management"></a>Gerenciamento de ativos

Como parte da implantação, você vai querer atualizar seu registro de ativos com o nome da sala, conta de recurso de entrada e dispositivos periféricos atribuídos.

## <a name="related-topics"></a>Tópicos relacionados

[Configurar contas para barras de colaboração do Microsoft Teams usando o Centro de administração do Microsoft Teams](resource-account-ui.md)

<!-- [Configure accounts for collaboration bars for Microsoft Teams using PowerShell](resource-account-ps.md) -->
