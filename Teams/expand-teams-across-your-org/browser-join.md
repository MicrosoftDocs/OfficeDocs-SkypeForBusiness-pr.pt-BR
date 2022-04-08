---
title: Gerenciar a experiência de junção Teams visitas virtuais em navegadores
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
description: Saiba mais sobre a experiência de ingresso Teams Visitas Virtuais em navegadores.
ms.openlocfilehash: 276e33b16972f0543566014adf264fd12e45c4ae
ms.sourcegitcommit: 1e8cff687b12348d4ecc538084ab57bbba23b523
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/07/2022
ms.locfileid: "64703737"
---
# <a name="manage-the-join-experience-for-teams-virtual-visits-on-browsers"></a>Gerenciar a experiência de junção Teams visitas virtuais em navegadores

Microsoft Teams torna mais fácil para as pessoas ingressarem em compromissos virtuais sem precisar baixar Teams. Para uma experiência mais perfeita, os participantes podem ingressar em compromissos, como visitas à saúde e consultas financeiras de um navegador da área de trabalho ou móvel. Os participantes não precisam instalar o aplicativo Teams em seus dispositivos.

Com o ingresso no navegador, quando um participante ingressa em um compromisso, ele não é solicitado a baixar Teams. Em vez Teams em um navegador, onde o participante pode selecionar Ingressar **agora** para ingressar. Com esse recurso, tenha em mente que, se Teams já estiver instalado no dispositivo, o Teams será aberto em um navegador e não no aplicativo.

Atualmente, o ingresso no navegador está disponível para compromissos agendados por meio do seguinte:

- [O Bookings aplicativo](https://support.microsoft.com/office/what-is-bookings-42d4e852-8e99-4d8f-9b70-d7fc93973cb5)
- Microsoft Teams EHR (Registro Eletrônico de Integridade)

  - Integração com [o Cerner EHR](healthcare/ehr-admin-cerner.md)
  - Integração com [o Epic EHR](healthcare/ehr-admin.md)

## <a name="set-up-browser-join"></a>Configurar a junção do navegador

### <a name="appointments-scheduled-through-the-bookings-app"></a>Compromissos agendados por meio do Bookings aplicativo

Os agendadores em sua organização podem ativar esse recurso para tipos de compromisso específicos e para compromissos individuais no Bookings aplicativo.

Depois que esse recurso estiver ativado, o email de confirmação ou o texto SMS enviado aos participantes conterá um link de ingresso na reunião que Teams em um navegador de área de trabalho ou móvel. Para obter uma lista de navegadores com suporte, consulte [Navegadores com suporte](#supported-browsers).

#### <a name="turn-on-browser-join-for-an-appointment-type"></a>Ativar a junção do navegador para um tipo de compromisso

Em Bookings, vá  >  para Configurações **Appointment**, selecione um tipo de compromisso e, em [](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887)seguida, ative Permitir que os participantes ingressem **em um navegador**. Isso permite o ingresso no navegador para todos os compromissos desse tipo.

:::image type="content" source="../media/browser-join-bookings-appointment-type.png" alt-text="Captura de tela da opção Permitir que os participantes ingressem em uma configuração do navegador para tipos de compromisso no Bookings aplicativo":::

#### <a name="turn-on-browser-join-for-an-individual-appointment"></a>Ativar a junção do navegador para um compromisso individual

No Bookings, selecione **Nova** reserva e, em seguida, ative Permitir que os participantes **ingressem em um navegador**.

:::image type="content" source="../media/browser-join-bookings-form.png" alt-text="Captura de tela da opção Permitir que os participantes ingressem em uma configuração do navegador no novo formulário de reserva no Bookings aplicativo":::

### <a name="appointments-scheduled-through-the-teams-ehr-connector"></a>Compromissos agendados por meio do Teams EHR

Nenhuma configuração é necessária para você ou sua equipe!

**Integração com o Cerner EHR**: o Teams EHR dá suporte a pacientes ingressando em compromissos virtuais por meio de um link na mensagem de texto SMS. No momento do compromisso, os pacientes podem ingressar tocando no link na mensagem de texto SMS e Teams abre em um navegador.

**Integração com o Epic EHR**: o conector Teams EHR dá suporte a pacientes que ingressam em compromissos virtuais por meio do MyChart Web e mobile. No momento do compromisso, os pacientes podem iniciar a visita do MyChart usando o botão Iniciar visita **virtual** e Teams abre em um navegador.

## <a name="supported-browsers"></a>Navegadores com suporte

Aqui estão os navegadores com suporte no momento. Damos suporte à versão mais recente, além de duas versões anteriores, a menos que indicado de outra forma.

|Plataforma  |Chrome |Safari |Edge (Chromium)|
|---------|:---|:---|:---:|
|Android   | &#x2714; &sup1;      |         |         |
|iOS    |         | &#x2714; &sup1; &sup2; |         |
|macOS     | &#x2714; | &#x2714;|         |
|Windows    | &#x2714; |   | &#x2714; |
|Ubuntu/Linux     | &#x2714;         |     |         |

&sup1; Não há suporte para o compartilhamento de tela de saída no iOS ou no Android.

&sup2; Os aplicativos iOS no Safari não podem selecionar dispositivos de microfone e alto-falante. Por exemplo, Bluetooth dispositivos. Essa é uma limitação do sistema operacional, que controla a seleção de dispositivo padrão.

## <a name="things-to-consider"></a>Coisas a serem consideradas

O membro da equipe que realiza a visita pode compartilhar sua tela de seu Teams desktop, móvel ou cliente Web com um participante que ingressa em um navegador da área de trabalho ou móvel. No entanto, os participantes não podem compartilhar a tela de um navegador da área de trabalho ou móvel.

## <a name="related-articles"></a>Artigos relacionados

- [Visitas virtuais com Teams e o Bookings aplicativo](bookings-virtual-visits.md)
- [Criar um tipo Bookings compromisso](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887)
- [Ingressar em um Bookings como participante](https://support.microsoft.com/office/join-a-bookings-appointment-as-an-attendee-95cea12d-2220-421f-a663-6efb20913c7f)
- [Visitas virtuais com Teams – Integração ao Cerner EHR](healthcare/ehr-admin-cerner.md)
- [Visitas virtuais com Teams – Integração ao Epic EHR](healthcare/ehr-admin.md)
