---
title: Implantar barras de colaboração do Microsoft Teams
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
description: Leia este artigo para saber mais sobre como implantar as barras de colaboração do Microsoft Teams.
ms.openlocfilehash: 41eb3335eef78f1da2c64b1df65443ba93d40159
ms.sourcegitcommit: b255db7ef816d1884c9c71af86a901bd83a1d9ab
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962902"
---
# <a name="deploy-collaboration-bars-for-microsoft-teams"></a>Implantar barras de colaboração do Microsoft Teams

A implantação de barras de colaboração do Microsoft Teams pode ser dividida nas seguintes fases:

- **Preparação do site** Confirme se seus locais de implantação (salas) atendem aos requisitos de implantação.
- **Preparação do serviço** Crie contas de recursos e atribua-as aos dispositivos ([consulte criar uma conta de recurso usando o centro de administração do Microsoft 365](resource-account-ui.md)). Embora seja recomendável usar uma licença de sala dedicada, uma conta de usuário final devidamente licenciada também pode entrar nas barras de colaboração.
- **Configuração e implantação** Configure as barras de colaboração nas salas e conecte os dispositivos periféricos de que você precisa (consulte a documentação do fabricante para as barras de colaboração).

Para gerenciar as barras de colaboração, você precisa ser um administrador global, administrador de serviços do teams ou administrador de dispositivo do teams. Para obter mais informações sobre funções de administrador, consulte [usar funções de administrador do Microsoft Teams para gerenciar o Teams](../using-admin-roles.md).

## <a name="site-readiness"></a>Preparação do site

Enquanto os dispositivos pedidos estão sendo entregues à sua organização, trabalhe com suas equipes de rede, instalações e áudio-visual para garantir que os requisitos de implantação sejam atendidos e que cada site e sala estejam prontos em termos de energia, rede e exibição.

Nossas recomendações para sites da barra de colaboração são:

- Salas de até 4 pessoas em tamanho
- Contas de recursos dedicados
- Exibições habilitadas para toque
- Cabeamento Ethernet
- QoS (qualidade de serviço) habilitada na rede para mídia do Microsoft Teams

Para obter considerações sobre a instalação física, consulte a documentação do fabricante e, se você tiver uma, aproveite a experiência da sua equipe de áudio-visual antes de instalar e montar telas e executar o cabeamento.

> [!TIP]
> Não deixe de conferir a [preparação da sua rede para](../prepare-network.md) o planejamento de largura de banda e a avaliação da adequação da sua rede para tráfego em tempo real.
>
> Não recomendamos colocar servidores proxy entre dispositivos do Teams e a Internet. Para obter mais informações sobre servidores proxy e equipes, consulte [servidores proxy para Teams](../proxy-servers-for-skype-for-business-online.md).

|    |     |
|-----------|------------|
| ![Um ícone representando pontos de decisão](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Confirme se seus sites atendem aos requisitos de preparação do site para barras de colaboração do Microsoft Teams.</li><li>Confirme que você forneceu largura de banda suficiente para cada site.</li></ul>|
| ![Um ícone que representa as próximas etapas](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Comece a planejar a implantação e a configuração da barra de colaboração.</li></ul>|

## <a name="service-readiness"></a>Prontidão de serviço

Antes de implantar as barras de colaboração, você precisa decidir se elas usarão contas de recursos do Microsoft 365, contas de usuário final ou uma mistura de ambas. As contas de recursos do Microsoft 365 são contas de caixa de correio e de equipe dedicadas a recursos específicos, como uma sala, um projetor e assim por diante. Essas contas de recursos podem responder automaticamente aos convites de reunião usando regras definidas quando são criadas. A menos que uma barra de colaboração seja dedicada a um indivíduo específico para seu uso particular, recomendamos configurar uma conta de recurso do Microsoft 365 para ele.

### <a name="using-a-resource-account"></a>Usar uma conta de recurso

Se você decidir configurar uma conta de recurso do Microsoft 365, precisará comprar uma licença da sala de reunião para ela. A licença da sala de reunião inclui uma caixa de correio de recurso que permite que as pessoas em sua organização submarquem a sala de reunião via Outlook ou Teams. A licença também permite a conferência de vídeo e áudio e o compartilhamento de tela entre os participantes da reunião.

Se precisar receber ou fazer chamadas para ou de um número de telefone externo, talvez seja necessário um plano de chamadas ou uma [licença do complemento](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing?tabs=small-business)Microsoft 365 Business Voice. Se o roteamento direto estiver habilitado em sua organização, você só precisará do SKU da sala de reunião.

Ao criar uma conta de recurso, você pode optar por permitir que a conta aceite ou recuse automaticamente solicitações de reunião, permita reuniões recorrentes, especifique até onde as pessoas adiantadas podem agendar o recurso e assim por diante.

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

Para obter mais informações sobre as barras de colaboração para contas de recursos do Microsoft 365, consulte [criar uma conta de recurso usando o centro de administração do microsoft 365](resource-account-ui.md).

|    |     |
|-----------|------------|
| ![Um ícone representando pontos de decisão](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida se deseja fazer ou receber chamadas telefônicas externas e identificar os requisitos de licenciamento para suas contas de recursos.</li></ul>|
| ![Um ícone que representa as próximas etapas](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Preparar contas de recursos.</li></ul>|

## <a name="configuration-and-deployment"></a>Configuração e implantação

O planejamento de configuração e implantação abrange as seguintes áreas-chave:

- Provisionamento de conta de recurso
- Implantação de dispositivos
- Barras de colaboração do aplicativo Microsoft Teams e configuração de dispositivo periférico
-  Testes
- Gerenciamento de ativos

### <a name="account-provisioning"></a>Provisionamento de conta

Se você planeja usar contas de recursos do Microsoft 365 para permitir que os usuários marquem as barras de colaboração, siga as instruções em [criar uma conta de recurso usando o centro de administração do microsoft 365](resource-account-ui.md) para criar uma conta de recurso do Microsoft 365 para cada barra de colaboração que precisa de um. Também é aí que você precisará adicionar uma licença da sala de reunião à conta do recurso e, se quiser fazer ou receber chamadas para ou de números de telefone externos, um plano de chamadas ou uma licença de voz para empresas, se sua organização não estiver usando o roteamento direto.

Se quiser atribuir barras de colaboração a usuários individuais para o uso particular, você não precisará configurar nenhuma conta adicional. Os usuários podem entrar nas barras de colaboração usando suas contas pessoais.

> [!TIP]
> Faça com que os nomes de exibição de suas contas de recursos do Microsoft 365 sejam descritivos e fáceis de entender. Estes são os nomes que os usuários verão ao pesquisar e adicionar barras de colaboração para o Microsoft Teams em reuniões. Você pode usar uma convenção como *Site* - *nome da sala*do site (*capacidade máxima da sala*), portanto, por exemplo Curie, uma sala de reunião de 4 pessoas em Londres, pode ter o nome de exibição Lon-Curie (4).

|    |     |
|-----------|------------|
| ![Um ícone representando pontos de decisão](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida a Convenção de nomenclatura para suas contas de recursos dedicados.</li><li>Decida se você criará contas individuais ou usará scripts de provisionamento em massa.</li></ul>|
| ![Um ícone que representa as próximas etapas](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Comece a planejar a implantação do seu dispositivo.</li></ul>|

### <a name="device-deployment"></a>Implantação de dispositivos

Em seguida, você precisa criar seu plano para entregar os dispositivos e seus dispositivos periféricos atribuídos a suas salas e, em seguida, prosseguir com a instalação e a configuração.

|    |     |
|-----------|------------|
| ![Um ícone representando pontos de decisão](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decidir quem vai gerenciar a implantação de site por site.</li><li> Identifique os recursos que instalarão as barras de colaboração do Microsoft Teams no site e realizar a configuração e os testes.</li></ul>|
| ![Um ícone que representa as próximas etapas](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Iniciar o teste de dispositivo.</li></ul>|

### <a name="testing"></a> Testes

Após a implantação das barras de colaboração do Microsoft Teams, você deve testá-las. Conecte-se ao dispositivo e verifique se os recursos esperados estão funcionando no dispositivo implantado. É altamente recomendável que você verifique se os dispositivos estão aparecendo na seção **barras de colaboração** na guia **dispositivos** do centro de administração do Microsoft Teams. Também é importante que você faça várias chamadas de teste e reuniões para verificar a qualidade e o desempenho.

Recomendamos que, como parte da implementação geral do Microsoft Teams, você configure a construção de arquivos para o painel de qualidade de chamada (CQD), monitore as tendências de qualidade e participe do processo de avaliação da qualidade da experiência. Para obter mais informações, consulte o [Guia de revisão da qualidade da experiência](https://aka.ms/qerguide).

### <a name="asset-management"></a>Gerenciamento de ativos

Como parte da implantação, você desejará atualizar o registro de ativos com o nome da sala, conta de recurso conectado e dispositivos periféricos atribuídos.

## <a name="related-topics"></a>Tópicos relacionados

[Configurar contas para barras de colaboração do Microsoft Teams usando o centro de administração do Microsoft Teams](resource-account-ui.md)

<!-- [Configure accounts for collaboration bars for Microsoft Teams using PowerShell](resource-account-ps.md) -->
