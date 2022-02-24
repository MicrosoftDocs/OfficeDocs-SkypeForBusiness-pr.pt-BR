---
title: Gerenciar a experiência de junção para Teams visitas virtuais em navegadores móveis
author: lanachin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: ''
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- microsoftcloud-healthcare
- microsoftcloud-retail
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: hafarmer
description: Saiba mais sobre a experiência de junção para Teams Visitas Virtuais em navegadores móveis.
ms.openlocfilehash: 698a87ba633892f5ebef864c60c101084aa296f1
ms.sourcegitcommit: 5ca04ee10e3f254e1b24506de116591fdfd51d18
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/23/2022
ms.locfileid: "62929316"
---
# <a name="manage-the-join-experience-for-teams-virtual-visits-on-mobile-browsers"></a>Gerenciar a experiência de junção para Teams visitas virtuais em navegadores móveis

Microsoft Teams torna mais fácil para as pessoas ingressarem em compromissos em seus dispositivos móveis sem precisar baixar Teams. Para uma experiência mais perfeita, os participantes podem ingressar em compromissos como consultas de saúde, consultas financeiras, horários de escritório de educadores e assim por diante, de um navegador móvel. Os participantes não precisam instalar o aplicativo móvel Teams em seus dispositivos móveis Android ou iOS.

Com a entrada do navegador móvel, quando um participante ins junta um compromisso de um dispositivo móvel, ele não é solicitado a baixar Teams. Em vez disso, Teams abre em um navegador móvel, onde o participante pode selecionar **Ingressar agora** para ingressar. Com esse recurso, lembre-se de que, se o Teams já estiver instalado no dispositivo móvel de um participante, o Teams abrirá em um navegador móvel e não no aplicativo.

Atualmente, a junção do navegador móvel está disponível para compromissos agendados por meio do seguinte:

- [O aplicativo Bookings](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-us&rs=en-us&ad=us#PickTab=Bookings)
- Microsoft Teams EHR (Registro Eletrônico de Saúde)

  - Integração com [Cerner EHR](healthcare/ehr-admin-cerner.md)
  - Integração com [o EHR Épico](healthcare/ehr-admin.md)

## <a name="set-up-mobile-browser-join"></a>Configurar a junção do navegador móvel

### <a name="appointments-scheduled-through-the-bookings-app"></a>Compromissos agendados por meio do aplicativo Bookings

Agendadores em sua organização podem ativar esse recurso para tipos de compromisso específicos e para compromissos individuais no aplicativo Bookings.

Depois que esse recurso for ligado, o email de confirmação ou texto SMS enviado aos participantes conterá um link de participação de reunião que abre Teams em um navegador móvel. Em dispositivos móveis Android, Teams abre no Chrome. Em dispositivos móveis iOS, Teams abre no Safari.

#### <a name="turn-on-mobile-browser-join-for-an-appointment-type"></a>Ativar a junção do navegador móvel para um tipo de compromisso

No Bookings, vá para os tipos **Configurações** >  **Appointment**, selecione um tipo de compromisso e, em [seguida,](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887) acione Permitir que os participantes participem **de um navegador móvel**. Isso permite que o navegador móvel participe de todos os compromissos desse tipo.

:::image type="content" source="../media/mobile-browser-join-bookings-appointment-type.png" alt-text="Captura de tela do permitir que os participantes participem de uma configuração de navegador móvel para tipos de compromisso no aplicativo Bookings":::

#### <a name="turn-on-mobile-browser-join-for-an-individual-appointment"></a>Ativar a junção do navegador móvel para um compromisso individual

No Bookings, selecione **Nova reserva** e, em seguida, acione Permitir que os participantes **participem de um navegador móvel**.

:::image type="content" source="../media/mobile-browser-join-bookings-form.png" alt-text="Captura de tela da configuração Permitir que os participantes participem de uma configuração do navegador móvel no novo formulário de reserva no aplicativo Bookings":::

### <a name="appointments-scheduled-through-the-teams-ehr-connector"></a>Compromissos agendados por meio do conector Teams EHR

Nenhuma configuração é necessária por você ou sua equipe!

**Integração com o Cerner EHR**: o conector Teams EHR oferece suporte a pacientes que inserem compromissos virtuais por meio de dispositivos móveis. No momento do compromisso, os pacientes podem participar tocando no link na mensagem de texto SMS. O paciente escolhe o navegador que deseja e, em seguida, Teams abre nesse navegador.

**Integração com o EHR Épico**: o conector Teams EHR oferece suporte a pacientes que ingressarem em compromissos virtuais por meio da Web e do MyChart para dispositivos móveis. No momento do compromisso, os pacientes podem iniciar a visita do MyChart usando o botão **Iniciar visita virtual** . O paciente escolhe o navegador que deseja e, em seguida, Teams abre nesse navegador.

## <a name="supported-mobile-browsers"></a>Navegadores móveis com suporte

Aqui estão os navegadores móveis com suporte no momento. Suportamos a versão mais recente, além de duas versões anteriores, a menos que indicado de outra forma.

|Plataforma  |Chrome |Safari |Borda (Chromium)|
|---------|:---:|:---:|:---:|
|Android   |   &#x2714;      |         |         |
|iOS    |         |  &#x2714; &sup1;       |         |
|macOS     |         |  &#x2714; &sup2;    |         |

&sup1; Os aplicativos iOS no Safari não podem selecionar dispositivos de microfone e alto-falante. Por exemplo, Bluetooth dispositivos. Essa é uma limitação do sistema operacional, que controla a seleção de dispositivo padrão.

&sup2; O Safari 14+ e o macOS 11+ são necessários para o suporte a vídeo de saída.

## <a name="things-to-consider"></a>Coisas a considerar

O membro da equipe que conduz a visita pode compartilhar sua tela de seu cliente Teams desktop, móvel ou Web com um participante que insinte de um navegador móvel. No entanto, os participantes não podem compartilhar sua tela de um navegador móvel.

> [!NOTE]
> Estamos adicionando mais recursos à experiência de junção de reunião em versões futuras do Teams, portanto, verifique novamente as informações mais atualizadas. Para ficar por dentro dos recursos Teams futuros, confira o [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams).

## <a name="related-articles"></a>Artigos relacionados

- [Visitas virtuais com Teams e o aplicativo Bookings](bookings-virtual-visits.md)
- [Criar um tipo de compromisso do Bookings](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887)
- [Ingressar em um compromisso do Bookings como participante](https://support.microsoft.com/office/join-a-bookings-appointment-as-an-attendee-95cea12d-2220-421f-a663-6efb20913c7f)
- [Visitas virtuais com Teams - Integração ao Cerner EHR](healthcare/ehr-admin-cerner.md)
- [Visitas virtuais com Teams - Integração ao EHR Épico](healthcare/ehr-admin.md)
