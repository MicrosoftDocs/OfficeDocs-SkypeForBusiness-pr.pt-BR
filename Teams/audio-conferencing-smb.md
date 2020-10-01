---
title: Configurar a videoconferência para empresas de pequeno e médio porte
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: jonorton, tonysmit
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
description: 'Saiba como configurar a conferência de áudio na sua pequena ou média empresa para as pessoas que precisam usar um telefone para fazer chamadas para reuniões. '
ms.openlocfilehash: 648a6342adf0fc035dcd33c6eb11efb40b0d4eed
ms.sourcegitcommit: 739ffd5893abf6d181877d1110f9dc8230b3bfd2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328428"
---
# <a name="set-up-audio-conferencing-for-small-and-medium-businesses"></a>Configurar a videoconferência para empresas de pequeno e médio porte

Com o áudio videoconferência, as pessoas podem fazer chamadas para reuniões do teams usando um telefone, em vez de usar o aplicativo Teams em seu dispositivo móvel ou do computador.  

Se você for uma pequena ou média empresa com até 300 usuários e não tiver nenhuma licença de audioconferência, você pode adquirir o áudio para conferências grátis por um ano. Esta oferta gratuita está disponível a partir de 1 ° de outubro de 2020.

A licença do complemento do Audio Conferencing pode ser aplicada a usuários que tenham licenças do Microsoft 365 Business Basic, Business Standard, Business Premium, Enterprise E1 ou Enterprise E3. Para saber mais, consulte [licenças de Complementos do Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

> [!NOTE]
> Se você tiver o Enterprise E5 ou o Microsoft 365 Business Voice, você não poderá usar a oferta de audioconferência de áudio gratuita, pois essas licenças já incluem videoconferência.

Neste artigo, vamos orientá-lo sobre como configurar a conferência de áudio. Basta configurar uma Audioconferência para as pessoas que planejam agendar ou liderar reuniões. Os participantes da reunião que fizerem chamadas para reuniões não precisam de licenças ou outras configurações. Para saber mais, confira [áudio videoconferência](audio-conferencing-in-office-365.md).

## <a name="step-1-get-audio-conferencing-licenses"></a>Etapa 1: obter licenças de audioconferência

Obtenha uma licença de conferência de áudio para cada pessoa que conduzirá reuniões. Use o centro de administração do Microsoft 365 para fazer isso.

1. No centro de administração do Microsoft 365, vá **Billing**para  >  **serviços de compra**de cobrança e, em seguida, na parte inferior da página, selecione Complementos. **Add-ons** 
2. Selecione detalhes da **promoção de adoção do Microsoft 365 Audio audioconferência**  >  **Details**.
3. Digite o número de licenças necessárias para os organizadores da reunião e conclua o seu pedido.

> [!NOTE]
> Marque ou desmarque a opção **atribuir automaticamente a todos os usuários sem licenças**, dependendo se você deseja atribuir automaticamente uma licença de audioconferência a todos os usuários que não têm essa licença.

## <a name="step-2-assign-an-audio-conferencing-license-to-users-who-lead-meetings"></a>Etapa 2: atribuir uma licença de audioconferência para os usuários que liderarem reuniões

Atribua uma licença a cada pessoa que conduzirá reuniões. Use o centro de administração do Microsoft 365 para fazer isso.

### <a name="assign-a-license-to-one-user"></a>Atribuir uma licença a um usuário

1. No centro de administração do Microsoft 365, vá **para usuários**  >  **ativos**do Microsoft.  
2. Selecione a linha do usuário à qual você deseja atribuir a licença e, em seguida, no painel, selecione **licenças e aplicativos**.
3. Marque a caixa de seleção **conferência de áudio da Microsoft 365** e, em seguida, selecione **salvar alterações**. 

### <a name="assign-a-license-to-multiple-users"></a>Atribuir uma licença a vários usuários

1. No centro de administração do Microsoft 365, vá **para usuários**  >  **ativos**do Microsoft.  
2. Selecione os círculos ao lado dos usuários aos quais você deseja atribuir a licença e, em seguida, selecione **gerenciar licenças de produto**.
3. No painel **gerenciar licenças de produto** , selecione **atribuir mais**.
4. Marque a caixa de seleção **conferência de áudio da Microsoft 365** e, em seguida, selecione **salvar alterações**.  

## <a name="step-3-find-or-get-a-phone-number-for-your-conferencing-bridge"></a>Etapa 3: localizar ou obter um número de telefone para a sua ponte de conferência

Você precisará de um número de telefone (também chamado de número de serviço) para a sua ponte de conferência para que possa ser usado em convites de reunião. Você pode optar por usar um **número compartilhado** ou um **número dedicado**. Os dois tipos de números podem ser usados por qualquer chamador para ingressar em uma reunião.

### <a name="use-a-shared-number"></a>Usar um número compartilhado

Um número compartilhado é um número compartilhado em todas as organizações. Os números compartilhados são atribuídos automaticamente quando você configura a conferência de áudio. Esses números compartilhados são números de chamada em que tarifas de longa distância podem ser aplicadas.

Para localizar o número padrão atribuído à sua ponte de conferência, no painel de navegação esquerdo do centro de administração do Microsoft Teams, vá para **reuniões**  >  **conferência Bridges**e, em seguida, localize o número para o local mais próximo de você.

### <a name="get-a-dedicated-number"></a>Obter um número exclusivo

Um número dedicado é um número que está disponível apenas para seus usuários. Um número dedicado pode ser um número de chamada tarifada ou um número de chamada gratuita. Para usar um número dedicado, você precisará primeiro obter o número e, em seguida, atribuí-lo à sua ponte de conferência.  

Há algumas maneiras de obter um número exclusivo. Você pode obter um número da Microsoft ou transferir (porta) um número existente de seu provedor de serviços atual para a Microsoft. Para saber mais sobre como fazer isso, consulte [obtendo números de serviço](getting-service-phone-numbers.md).

> [!NOTE]
> Se você usa um número de chamada gratuita, é preciso primeiro atribuir uma licença de créditos de comunicações a cada pessoa que conduzirá reuniões. Para saber mais, confira [Configurar créditos de comunicações para a sua organização](set-up-communications-credits-for-your-organization.md).

Depois de ter seu número, atribua-o à sua ponte de conferência. Use o centro de administração do Microsoft Teams para fazer isso.

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para **reuniões**  >  **conferência pontes**.
2. Selecione **Adicionar**e, em seguida, selecione **número de chamada** ou número **de chamada gratuita**.
3. No painel **Adicionar número de telefone** , selecione o número e, em seguida, selecione **aplicar**.

## <a name="step-4-assign-a-dial-in-number-to-users-who-lead-meetings"></a>Etapa 4: atribuir um número de discagem aos usuários que liderarem reuniões

Atribua um número de discagem para cada pessoa que iniciará reuniões. Use o centro de administração do Microsoft Teams para fazer isso.

1. Na navegação à esquerda do centro de administração do Microsoft Teams, selecione **usuários**, clique no nome de exibição do usuário e selecione **Editar**.
2. Selecione **Editar**   ao lado de **videoconferência**e, em seguida, no painel **conferência de áudio**   , selecione um número nas listas **número de chamada**ou número de    **chamada gratuita**   e, em seguida, selecione **aplicar**.

## <a name="step-5-schedule-a-teams-meeting-in-outlook"></a>Etapa 5: agendar uma reunião do teams no Outlook

Para agendar uma reunião, no Outlook, vá para **calendário**e selecione o botão **nova reunião do teams** . Os números de discagem que você define para o usuário e a ID da conferência são automaticamente adicionados ao convite da reunião que é enviado aos participantes da reunião.

Para saber mais, consulte [agendar uma reunião do teams no Outlook](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f).

> [!NOTE]
> Se desejar, você pode personalizar convites de reunião para adicionar o logotipo da sua empresa, links para seu site de suporte e isenção de responsabilidade legal e um rodapé somente texto. Consulte [Personalizar convites da reunião](meeting-settings-in-teams.md#customize-meeting-invitations)

## <a name="related-topics"></a>Tópicos relacionados

- [Audioconferência](audio-conferencing-in-office-365.md)
- [Configurar a conferência de áudio para o Teams](set-up-audio-conferencing-in-teams.md)
- [Perguntas comuns sobre a Audioconferência](audio-conferencing-common-questions.md)
- [Obtendo números de serviço](getting-service-phone-numbers.md)
- [Licenças de Complementos do teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [Atribuir licenças a usuários](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)
