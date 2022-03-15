---
title: Implantar Salas do Microsoft Teams no Android
ms.author: czawideh
author: cazawideh
manager: serdars
audience: ITPro
ms.reviewer: payurevi
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Leia este artigo para saber mais sobre como implantar Salas do Microsoft Teams no Android.
ms.openlocfilehash: 55e410b1863effd671f08cba663211b78f76e30f
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503538"
---
# <a name="deploy-microsoft-teams-rooms-on-android"></a>Implantar Salas do Microsoft Teams no Android

A implantação Salas do Microsoft Teams no Android pode ser dividida nas seguintes fases:

- **Preparação do site** Confirme se seus locais de implantação (salas) atendem aos requisitos de implantação.
- **Preparação do serviço** Crie contas de recursos e atribua-as aos dispositivos ([consulte Create a resource account using the Centro de administração do Microsoft 365](resource-account-ui.md)). Embora seja recomendável usar uma licença de sala dedicada, uma conta de usuário final corretamente licenciada também pode entrar Salas do Teams no Android.
- **Configuração e implantação** Configurar Salas do Teams e conectar os dispositivos periféricos necessários (consulte a documentação do fabricante para obter detalhes).

Para gerenciar Salas do Teams, você precisa ser um administrador global, um administrador do serviço Teams ou um administrador Teams Device. Para obter mais informações sobre funções de administrador, consulte [Use Microsoft Teams de administrador para gerenciar Teams](../using-admin-roles.md).

## <a name="site-readiness"></a>Preparação do site

Enquanto os dispositivos ordenados estão sendo entregues à sua organização, trabalhe com suas equipes de rede, instalações e áudio-visuais para garantir que os requisitos de implantação sejam atendidos e que cada site e sala esteja pronto em termos de energia, rede e exibição.

Nossas recomendações para sites de barra de colaboração são:

- Salas com até 5 pessoas no tamanho
- Contas de recurso dedicadas
- Exibições habilitadas para toque
- Cabeamento Ethernet
- Qualidade do Serviço (QoS) habilitada na rede para Microsoft Teams mídia

Para considerações sobre a instalação física, consulte a documentação do fabricante e, se você tiver uma, aproveite a experiência da sua equipe audiovisual antes de instalar e montar telas e executar o cabeamento.

> [!TIP]
> Certifique-se de fazer check-out [Prepare your network for Teams](../prepare-network.md) for bandwidth planning and assessing your network's suitability for real-time traffic.
>
> Não recomendamos a colocação de servidores proxy entre Teams dispositivos e a Internet. Para obter mais informações sobre servidores proxy e Teams, confira [Servidores proxy para](../proxy-servers-for-skype-for-business-online.md) Teams.

|&nbsp;|&nbsp;|
|-----------|------------|
| ![Um ícone representando pontos de decisão.](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Confirme se seus sites atendem aos requisitos de preparação do site para barras de colaboração para Microsoft Teams.</li><li>Confirme se você forneceu largura de banda suficiente para cada site.</li></ul>|
| ![Um ícone que representa as próximas etapas.](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Comece a planejar a implantação e a configuração da barra de colaboração.</li></ul>|

## <a name="service-readiness"></a>Prontidão de serviço

Antes de implantar Salas do Teams, você precisa decidir se elas usarão contas de recursos Microsoft 365, contas de usuário final ou uma mistura de ambas. Microsoft 365 contas de recursos são caixas de correio e Teams que são dedicadas a recursos específicos, como sala, projetor e assim por diante. Essas contas de recursos podem responder automaticamente a convites de reunião usando regras definidas quando elas são criadas. A menos Salas do Teams seja dedicada a um indivíduo específico para seu uso particular, recomendamos configurar uma conta Microsoft 365 de recursos para ela.

### <a name="using-a-resource-account"></a>Usando uma conta de recurso

Se você decidir configurar uma conta de recurso Microsoft 365, precisará comprar uma Sala de Reunião para ela. A Sala de Reunião inclui uma caixa de correio de recurso que permite que as pessoas em sua organização reservem a sala de reunião por meio de Outlook ou Teams. A licença também permite vídeo e audioconferência e compartilhamento de tela entre os participantes da reunião.

Se você precisar receber ou fazer chamadas para ou de um número de telefone externo, talvez seja necessário um Plano de Chamadas ou uma Microsoft 365 Business Voice [de complemento](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md?tabs=small-business). Se você tiver o Roteamento Direto habilitado em sua organização, você só precisará do SKU Sala de Reunião.

Ao criar uma conta de recurso, você pode escolher se a conta pode aceitar ou recusar automaticamente solicitações de reunião, permitir reuniões recorrentes, especificar até que ponto as pessoas podem reservar o recurso e assim por diante.

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

Para obter mais informações sobre Microsoft 365 de recursos, consulte [Create a resource account using the Centro de administração do Microsoft 365](resource-account-ui.md).

|&nbsp;|&nbsp;|
|-----------|------------|
| ![Um ícone representando pontos de decisão.](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida se deseja fazer ou receber chamadas telefônicas externas e identificar requisitos de licenciamento para suas contas de recursos.</li></ul>|
| ![Um ícone que representa as próximas etapas.](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Preparar contas de recursos.</li></ul>|

## <a name="configuration-and-deployment"></a>Configuração e implantação

O planejamento de configuração e implantação abrange as seguintes áreas principais:

- Provisionamento de conta de recursos
- Implantação de dispositivo
- Salas do Teams aplicativo e configuração de dispositivo periférico
-  Testes
- Gerenciamento de ativos

### <a name="account-provisioning"></a>Provisionamento de conta

Se você planeja usar Microsoft 365 de recursos para permitir que os usuários reservem barras de colaboração, siga as instruções em Criar uma conta de recurso usando o [Centro de administração do Microsoft 365](resource-account-ui.md) para criar uma conta de recurso Microsoft 365 para cada barra de colaboração que precise de uma. Também é onde você precisará adicionar uma licença de Sala de Reunião à conta de recurso e, se você quiser fazer ou receber chamadas para ou de números de telefone externos, uma licença de Plano de Chamadas ou Business Voice se sua organização não estiver usando Roteamento Direto.

Se você deseja atribuir Salas do Teams usuários individuais para uso particular, não é necessário configurar nenhuma conta adicional. Os usuários podem entrar em barras de colaboração usando suas contas pessoais.

> [!TIP]
> Tornar os nomes de exibição para suas Microsoft 365 de recursos descritivos e fáceis de entender. Esses são os nomes que os usuários verão ao pesquisar e adicionar Salas do Teams reuniões. Você pode usar uma convenção como *Nome do SiteRoom*-(*Max Room Capacity*), portanto, por exemplo, Curie, uma sala de reunião de 4 pessoas em Londres, pode ter o nome de exibição LON-CURIE(4).

|&nbsp;|&nbsp;|
|-----------|------------|
| ![Um ícone representando pontos de decisão.](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida a convenção de nomenistura para suas contas de recursos dedicadas.</li><li>Decida se você criará contas individuais ou usará scripts de provisionamento em massa.</li></ul>|
| ![Um ícone que representa as próximas etapas.](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Comece a planejar a implantação do dispositivo.</li></ul>|

### <a name="device-deployment"></a>Implantação de dispositivo

Em seguida, você precisa criar seu plano para entregar os dispositivos e seus dispositivos periféricos atribuídos às suas salas e, em seguida, prosseguir com a instalação e a configuração.

|&nbsp;|&nbsp;|
|-----------|------------|
| ![Um ícone representando pontos de decisão.](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida quem gerenciará a implantação site a site.</li><li> Identifique os recursos que instalarão Salas do Teams local e realizar a configuração e o teste.</li></ul>|
| ![Um ícone que representa as próximas etapas.](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Inicie o teste do dispositivo.</li></ul>|

### <a name="testing"></a> Testes

Depois de Salas do Teams, você deve testá-los. Entre no Salas do Teams e verifique se os recursos esperados estão funcionando. É altamente recomendável que você verifique se elas estão aparecendo na  seção Barras de colaboração na guia dispositivos **Teams** do Microsoft Teams de administração. Também é importante que você faça várias chamadas de teste e reuniões para verificar a qualidade e o desempenho.

Recomendamos que, como parte da Microsoft Teams geral, você configure a criação de arquivos para o Painel de Qualidade de Chamada (CQD), monitore tendências de qualidade e participe do processo de Revisão da Qualidade da Experiência. Para obter mais informações, consulte o [Guia de Revisão de Qualidade da Experiência](../quality-of-experience-review-guide.md).

### <a name="asset-management"></a>Gerenciamento de ativos

Como parte da implantação, você deseja atualizar seu registro de ativo com o nome da sala, conta de recurso conectado e dispositivos periféricos atribuídos.

## <a name="related-topics"></a>Tópicos relacionados

[Configurar contas para Salas do Microsoft Teams usando Microsoft Teams centro de administração](resource-account-ui.md)

<!-- [Configure accounts for collaboration bars for Microsoft Teams using PowerShell](resource-account-ps.md) -->