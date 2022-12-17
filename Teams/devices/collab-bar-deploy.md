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
- Teams_ITAdmin_Devices
ms.custom: ''
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Leia este artigo para saber mais sobre como implantar Salas do Microsoft Teams no Android.
ms.openlocfilehash: 52b865879db3941b5631d7b22c25bd8f6e4d3ce6
ms.sourcegitcommit: b710fc61558a0e031d4e3e4000f234c495e2c4c6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2022
ms.locfileid: "69438409"
---
# <a name="deploy-microsoft-teams-rooms-on-android"></a>Implantar Salas do Microsoft Teams no Android

A implantação de Salas do Microsoft Teams no Android pode ser dividida nas seguintes fases:

- **Preparação do site** Confirme se os locais de implantação (salas) atendem aos requisitos de implantação.
- **Preparação do serviço** Crie contas de recurso e atribua-as aos dispositivos ([consulte Criar uma conta de recurso usando o Centro de administração do Microsoft 365](resource-account-ui.md)). Embora seja recomendável usar uma licença de sala dedicada, uma conta de usuário final devidamente licenciada também pode entrar no Salas do Teams no Android.
- **Configuração e implantação** Configure Salas do Teams e conecte os dispositivos periféricos necessários (consulte a documentação do fabricante para obter detalhes).

Para gerenciar Salas do Teams, você precisa ser um administrador global, administrador do Serviço do Teams ou administrador do Dispositivo do Teams. Para obter mais informações sobre funções de administrador, consulte [Usar Microsoft funções de administrador do Teams para gerenciar o Teams](../using-admin-roles.md).

## <a name="site-readiness"></a>Preparação do site

Enquanto os dispositivos ordenados estão sendo entregues à sua organização, trabalhe com suas equipes de rede, instalações e audiovisual para garantir que os requisitos de implantação sejam atendidos e cada site e sala esteja pronto em termos de energia, rede e exibição.

Nossas recomendações para Salas do Teams em sites Android são:

- Salas com até 5 pessoas de tamanho
- Contas de recursos dedicadas
- Exibições habilitadas para toque
- Cabeamento Ethernet
- QoS (Qualidade do Serviço) habilitado na rede para Microsoft mídia do Teams

Para considerações de instalação física, consulte a documentação do fabricante e, se você tiver uma, aproveite a experiência de sua equipe de audiovisual antes de instalar e montar telas e executar o cabeamento.

> [!TIP]
> Confira [Preparar sua rede para o Teams para](../prepare-network.md) planejamento de largura de banda e avaliar a adequação da rede para o tráfego em tempo real.
>
> Não recomendamos colocar servidores proxy entre dispositivos do Teams e a Internet. Para obter mais informações sobre servidores proxy e Teams, confira [Servidores proxy para o Teams](../proxy-servers-for-skype-for-business-online.md).

|&nbsp;|&nbsp;|
|-----------|------------|
| ![Um ícone representando pontos de decisão.](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Confirme se seus sites atendem aos requisitos de preparação do site para Salas do Teams no Android.</li><li>Confirme se você forneceu largura de banda suficiente para cada site.</li></ul>|
| ![Um ícone que mostra as próximas etapas.](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Comece a planejar seu Salas do Teams na implantação e configuração do Android.</li></ul>|

## <a name="service-readiness"></a>Prontidão de serviço

Antes de implantar Salas do Teams, você precisa decidir se eles usarão Microsoft 365 contas de recursos, contas de usuário final ou uma mistura de ambos. Microsoft 365 contas de recurso são contas de caixa de correio e do Teams dedicadas a recursos específicos, como uma sala, projetor e assim por diante. Essas contas de recurso podem responder automaticamente aos convites de reunião usando regras que você define quando são criadas. A menos que Salas do Teams seja dedicado a um indivíduo específico para seu uso privado, recomendamos configurar uma conta de recursos Microsoft 365 para ele.

### <a name="using-a-resource-account"></a>Usando uma conta de recurso

Se você decidir configurar uma conta de recursos Microsoft 365, precisará comprar uma licença da Sala de Reunião para ela. A licença da Sala de Reunião inclui uma caixa de correio de recursos que permite que as pessoas em sua organização reservem a sala de reunião por meio do Outlook ou do Teams. A licença também permite a conferência de vídeo e áudio e o compartilhamento de tela entre os participantes da reunião.

Se você precisar receber ou fazer chamadas para ou de um número de telefone externo, talvez precise de um Plano de Chamada ou Microsoft 365 Business Voice [licença de complemento](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md?tabs=small-business). Se você tiver o Roteamento Direto habilitado em sua organização, precisará apenas do SKU da Sala de Reunião.

Ao criar uma conta de recurso, você pode escolher se deseja permitir que a conta aceite ou recuse automaticamente as solicitações de reunião, permita reuniões recorrentes, especifique até onde as pessoas podem reservar o recurso com antecedência e assim por diante.

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

Para obter mais informações sobre Microsoft 365 contas de recursos, consulte [Criar uma conta de recurso usando o Centro de administração do Microsoft 365](resource-account-ui.md).

|&nbsp;|&nbsp;|
|-----------|------------|
| ![Um ícone representando pontos de decisão.](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida se deseja fazer ou receber chamadas telefônicas externas e identificar requisitos de licenciamento para suas contas de recursos.</li></ul>|
| ![Um ícone que mostra as próximas etapas.](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Preparar contas de recursos.</li></ul>|

## <a name="configuration-and-deployment"></a>Configuração e implantação

O planejamento de configuração e implantação abrange as seguintes áreas-chave:

- Provisionamento de conta de recursos
- Implantação do dispositivo
- Salas do Teams configuração de dispositivo periférico e aplicativo
-  Testes
- Gerenciamento de ativos

### <a name="account-provisioning"></a>Provisionamento de conta

Se você planeja usar Microsoft 365 contas de recursos para permitir que os usuários reservem Salas do Teams em dispositivos Android, siga as instruções em [Criar uma conta de recurso usando o Centro de administração do Microsoft 365](resource-account-ui.md) para criar uma conta de recursos Microsoft 365 para cada um Salas do Teams no dispositivo Android que precisa de um. É também aqui que você precisará adicionar uma licença da Sala de Reunião à conta de recursos e, se quiser fazer ou receber chamadas para ou de números de telefone externos, um Plano de Chamada ou licença do Business Voice se sua organização não estiver usando o Roteamento Direto.

Se você quiser atribuir Salas do Teams a usuários individuais para seu uso privado, não precisará configurar nenhuma conta adicional. Os usuários podem entrar em Salas do Teams em dispositivos Android usando suas contas pessoais.

> [!TIP]
> Torne os nomes de exibição de suas contas de recursos Microsoft 365 descritivas e fáceis de entender. Esses são os nomes que os usuários verão ao pesquisar e adicionar Salas do Teams às reuniões. Você pode usar uma convenção como *Nome da Sala* *do Site*- (*Capacidade Máxima da Sala*), portanto, por exemplo, Curie, uma sala de reunião de quatro pessoas em Londres, pode ter o nome de exibição LON-CURIE(4).

|&nbsp;|&nbsp;|
|-----------|------------|
| ![Um ícone representando pontos de decisão.](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida a convenção de nomenclatura para suas contas de recursos dedicadas.</li><li>Decida se você criará contas individuais ou usará scripts de provisionamento em massa.</li></ul>|
| ![Um ícone que mostra as próximas etapas.](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Comece a planejar a implantação do dispositivo.</li></ul>|

### <a name="device-deployment"></a>Implantação do dispositivo

Em seguida, você precisa criar seu plano para entregar os dispositivos e seus dispositivos periféricos atribuídos para suas salas e, em seguida, continuar com a instalação e a configuração.

|&nbsp;|&nbsp;|
|-----------|------------|
| ![Um ícone representando pontos de decisão.](../media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida quem gerenciará a implantação site a site.</li><li> Identifique os recursos que instalarão Salas do Teams no local e realizem a configuração e o teste.</li></ul>|
| ![Um ícone que mostra as próximas etapas.](../media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Inicie o teste de dispositivo.</li></ul>|

### <a name="testing"></a> Testes

Depois de implantar Salas do Teams, você deve testá-los. Entre no Salas do Teams e verifique se os recursos esperados estão funcionando. É altamente recomendável verificar se eles aparecem na seção **Salas do Teams no Android na** guia **Dispositivos teams** do centro de administração do Microsoft Teams. Também é importante que você faça várias chamadas de teste e reuniões para verificar a qualidade e o desempenho.

Recomendamos que, como parte da distribuição geral do Microsoft Teams, você configure arquivos de criação para CQD (Painel de Qualidade de Chamada), monitore tendências de qualidade e participe do processo de Revisão de Qualidade da Experiência. Para obter mais informações, consulte o [Guia de Revisão de Qualidade da Experiência](../quality-of-experience-review-guide.md).

### <a name="asset-management"></a>Gerenciamento de ativos

Como parte da implantação, você deseja atualizar o registro de ativos com o nome da sala, a conta de recursos de entrada e os dispositivos periféricos atribuídos.

## <a name="related-topics"></a>Tópicos relacionados

[Criar contas de recurso para salas e dispositivos do Teams compartilhados](../rooms/with-office-365.md)