---
title: Implantar Salas do Microsoft Teams no Android
ms.author: dstrome
author: dstrome
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
ms.openlocfilehash: d97af4854ca276d1d5a31f2990e607f357b01f58
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2022
ms.locfileid: "65761113"
---
# <a name="deploy-microsoft-teams-rooms-on-android"></a>Implantar Salas do Microsoft Teams no Android

A implantação Salas do Microsoft Teams no Android pode ser dividida nas seguintes fases:

- **Preparação do site** Confirme se seus locais de implantação (salas) atendem aos requisitos de implantação.
- **Preparação do serviço** Crie contas de recursos e atribua-as aos dispositivos ([consulte Criar uma conta de recurso usando o Centro de administração do Microsoft 365](resource-account-ui.md)). Embora seja recomendável usar uma licença de sala dedicada, uma conta de usuário final corretamente licenciada também pode entrar no Salas do Teams no Android.
- **Configuração e implantação** Configure o Salas do Teams e conecte os dispositivos periféricos necessários (consulte a documentação do fabricante para obter detalhes).

Para gerenciar Salas do Teams, você precisa ser um administrador global, administrador do serviço Teams ou administrador Teams dispositivo. Para obter mais informações sobre funções de administrador, [consulte Usar Microsoft Teams de administrador para gerenciar Teams](../using-admin-roles.md).

## <a name="site-readiness"></a>Preparação do site

Enquanto os dispositivos ordenados estão sendo entregues à sua organização, trabalhe com suas equipes de rede, instalações e áudio-visuais para garantir que os requisitos de implantação sejam atendidos e que cada site e sala esteja pronto em termos de energia, rede e exibição.

Nossas recomendações para sites de barras de colaboração são:

- Salas com até 5 pessoas de tamanho
- Contas de recursos dedicadas
- Exibições habilitadas para toque
- Cabeamento Ethernet
- QoS (Qualidade de Serviço) habilitada na rede para Microsoft Teams mídia

Para obter considerações sobre a instalação física, consulte a documentação do fabricante e, se você tiver uma, aproveite a experiência da sua equipe de áudio-visual antes de instalar e montar telas e executar o cabeamento.

> [!TIP]
> Certifique-se de fazer check-out Preparar sua rede [para Teams](../prepare-network.md) planejamento de largura de banda e avaliar a adequação da rede para tráfego em tempo real.
>
> Não recomendamos colocar servidores proxy entre Teams e a Internet. Para obter mais informações sobre servidores proxy e Teams, confira [servidores proxy para Teams](../proxy-servers-for-skype-for-business-online.md).

|&nbsp;|&nbsp;|
|-----------|------------|
| ![Um ícone representando pontos de decisão.](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Confirme se seus sites atendem aos requisitos de preparação do site para barras de colaboração para Microsoft Teams.</li><li>Confirme se você forneceu largura de banda suficiente para cada site.</li></ul>|
| ![Um ícone ilustrando as próximas etapas.](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Comece a planejar a implantação e a configuração da barra de colaboração.</li></ul>|

## <a name="service-readiness"></a>Prontidão de serviço

Antes de implantar Salas do Teams, você precisa decidir se elas usarão Microsoft 365 de recursos, contas de usuário final ou uma combinação de ambas. Microsoft 365 de recursos são contas de caixa de correio e Teams que são dedicadas a recursos específicos, como uma sala, projetor e assim por diante. Essas contas de recursos podem responder automaticamente a convites de reunião usando regras que você define quando são criadas. A menos Salas do Teams seja dedicada a um indivíduo específico para seu uso privado, recomendamos configurar uma Microsoft 365 de recursos para ela.

### <a name="using-a-resource-account"></a>Usando uma conta de recurso

Se você decidir configurar uma conta Microsoft 365 de recursos, precisará comprar uma Sala de Reunião para ela. A Sala de Reunião inclui uma caixa de correio de recurso que permite que as pessoas em sua organização reservem a sala de reunião por meio de Outlook ou Teams. A licença também permite vídeo e audioconferência e compartilhamento de tela entre os participantes da reunião.

Se você precisar receber ou fazer chamadas de ou para um número de telefone externo, talvez precise de um Plano de Chamada ou Microsoft 365 Business Voice [licença de complemento](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md?tabs=small-business). Se você tiver o Roteamento Direto habilitado em sua organização, só precisará do SKU Sala de Reunião serviço.

Ao criar uma conta de recurso, você pode optar por permitir que a conta aceite ou recuse automaticamente as solicitações de reunião, permita reuniões recorrentes, especifique até que ponto as pessoas podem reservar o recurso e assim por diante.

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

Para obter mais informações sobre Microsoft 365 de recursos, consulte [Criar uma conta de recurso usando o Centro de administração do Microsoft 365](resource-account-ui.md).

|&nbsp;|&nbsp;|
|-----------|------------|
| ![Um ícone representando pontos de decisão.](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida se deseja fazer ou receber chamadas telefônicas externas e identificar os requisitos de licenciamento para suas contas de recursos.</li></ul>|
| ![Um ícone ilustrando as próximas etapas.](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Preparar contas de recursos.</li></ul>|

## <a name="configuration-and-deployment"></a>Configuração e implantação

O planejamento de configuração e implantação abrange as seguintes áreas principais:

- Provisionamento de conta de recurso
- Implantação de dispositivo
- Salas do Teams aplicativo e configuração de dispositivo periférico
-  Testes
- Gerenciamento de ativos

### <a name="account-provisioning"></a>Provisionamento de conta

Se você planeja usar contas de recursos do Microsoft 365 para permitir que os usuários reservem barras de colaboração, siga as instruções em Criar uma conta de recurso usando o [Centro de administração do Microsoft 365](resource-account-ui.md) para criar uma conta de recurso do Microsoft 365 para cada barra de colaboração que precise de uma. Também é aqui que você precisará adicionar uma licença do Sala de Reunião à conta de recurso e, se quiser fazer ou receber chamadas de números de telefone externos, um Plano de Chamada ou uma licença do Business Voice se sua organização não estiver usando o Roteamento Direto.

Se você quiser atribuir Salas do Teams usuários individuais para seu uso privado, não precisará configurar nenhuma conta adicional. Os usuários podem entrar em barras de colaboração usando suas contas pessoais.

> [!TIP]
> Torne os nomes de exibição para suas Microsoft 365 de recursos descritivos e fáceis de entender. Esses são os nomes que os usuários verão ao pesquisar e adicionar Salas do Teams reuniões. Você pode usar uma convenção como Nome da Sala de *Sites*-*(Capacidade* Máxima de *Sala), portanto*, por exemplo, Curie, uma sala de reunião de 4 pessoas em Londres, pode ter o nome de exibição LON-CURIE(4).

|&nbsp;|&nbsp;|
|-----------|------------|
| ![Um ícone representando pontos de decisão.](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida a convenção de nomenclatura para suas contas de recursos dedicadas.</li><li>Decida se você criará contas individuais ou usará scripts de provisionamento em massa.</li></ul>|
| ![Um ícone ilustrando as próximas etapas.](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Comece a planejar a implantação do dispositivo.</li></ul>|

### <a name="device-deployment"></a>Implantação de dispositivo

Em seguida, você precisa criar seu plano para entregar os dispositivos e seus dispositivos periféricos atribuídos às suas salas e, em seguida, prosseguir com a instalação e a configuração.

|&nbsp;|&nbsp;|
|-----------|------------|
| ![Um ícone representando pontos de decisão.](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida quem gerenciará a implantação site a site.</li><li> Identifique os recursos que instalarão o Salas do Teams local e realizem a configuração e o teste.</li></ul>|
| ![Um ícone ilustrando as próximas etapas.](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Inicie o teste de dispositivo.</li></ul>|

### <a name="testing"></a> Testes

Depois de implantar o Salas do Teams, você deve testá-los. Entre no Salas do Teams e verifique se os recursos esperados estão funcionando. É altamente recomendável que você verifique se eles estão aparecendo na  seção Barras de colaboração na guia Teams **Dispositivos** do Microsoft Teams de administração. Também é importante que você faça várias chamadas de teste e reuniões para verificar a qualidade e o desempenho.

Recomendamos que, como parte da distribuição geral do Microsoft Teams, você configure a criação de arquivos para o Painel de Qualidade de Chamadas (CQD), monitore as tendências de qualidade e participe do processo de Revisão de Qualidade da Experiência. Para obter mais informações, consulte o [Guia de Revisão de Qualidade da Experiência](../quality-of-experience-review-guide.md).

### <a name="asset-management"></a>Gerenciamento de ativos

Como parte da implantação, você desejará atualizar seu registro de ativo com o nome da sala, a conta de recurso conectada e os dispositivos periféricos atribuídos.

## <a name="related-topics"></a>Tópicos relacionados

[Criar contas de recursos para salas e dispositivos Teams compartilhados](../rooms/with-office-365.md)