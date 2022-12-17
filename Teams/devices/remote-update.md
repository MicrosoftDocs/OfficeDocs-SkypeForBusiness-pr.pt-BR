---
title: Atualizar dispositivos Microsoft Teams remotamente
ms.author: dstrome
author: dstrome
ms.reviewer: rahulmi
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Devices
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Atualize Microsoft telefones do Teams, painéis do Teams e Salas do Teams no Android, dispositivos usando remotamente o centro de administração do Teams.
ms.openlocfilehash: c69a4deb43df5d40bf158a3c5bc467d431b041d5
ms.sourcegitcommit: b710fc61558a0e031d4e3e4000f234c495e2c4c6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2022
ms.locfileid: "69438259"
---
# <a name="update-microsoft-teams-devices-remotely"></a>Atualizar dispositivos Microsoft Teams remotamente

Usando o centro de administração do Microsoft Teams, você pode atualizar seus dispositivos teams, como telefones do Teams, painéis do Teams e Salas do Teams no Android, remotamente. Os seguintes componentes de software em seu dispositivo podem ser atualizados do centro de administração do Teams:

- Aplicativo Teams
- Firmware de dispositivo

As atualizações de firmware do dispositivo acontecem automaticamente por padrão. No entanto, você pode atualizar o firmware e outros componentes de software manualmente. Ao aplicar atualizações manualmente, elas podem ser aplicadas imediatamente ou agendadas para uma data e hora futuras.

Somente as versões de firmware que foram testadas por Microsoft estão disponíveis para atualização automática ou manual por meio do centro de administração do Teams. As versões de firmware testadas por Microsoft são rotuladas como **Verificadas por Microsoft**. As versões de firmware que não foram testadas pelo Microsoft são rotuladas como **Versão desconhecida**. Os dispositivos que executam uma versão de firmware desconhecido não podem ser atualizados automaticamente; esses dispositivos só podem ser atualizados manualmente.

Para gerenciar dispositivos, você precisa ser um administrador global, administrador do Serviço do Teams ou administrador do Dispositivo do Teams. Para obter mais informações sobre funções de administrador, consulte [Usar Microsoft funções de administrador do Teams para gerenciar o Teams](../using-admin-roles.md).

## <a name="assign-devices-to-an-automatic-update-phase"></a>Atribuir dispositivos a uma fase de atualização automática

Atribuir dispositivos a uma fase de atualização automática é um recurso Salas Teams Pro para Salas do Teams em dispositivos Android. Dispositivos com uma licença Salas do Teams Basic serão atribuídos à fase Geral. Qualquer fase pré-configurada será mantida e nenhuma alteração adicional será permitida. Para obter mais informações, consulte [Salas do Microsoft Teams licenças](../rooms/rooms-licensing.md).  

As atualizações automáticas de dispositivos do Teams usando o centro de administração do Teams não estão disponíveis no GCC High. No entanto, as organizações no GCC High podem [atualizar manualmente os dispositivos do Teams](#manually-update-remote-devices) usando o centro de administração do Teams.

> [!IMPORTANT]
> O recurso de atualização automática está atualmente em versão antecipada. Atualizações pode ser implantado mais lentamente do que a fase selecionada. Nos próximos meses, a velocidade com que as atualizações são implantadas automaticamente aumentará até que elas cheguem à fase selecionada.

> [!NOTE]
> Alguns dispositivos ainda não dão suporte a atualizações automáticas de firmware. A aplicação de configurações automáticas de atualização de firmware em dispositivos que não dão suporte a atualizações automáticas não terá nenhum efeito nesses dispositivos. Para obter dúvidas sobre se seu dispositivo dará suporte a atualizações automáticas de firmware, entre em contato com o fabricante do dispositivo.
>
> Atualizações são aplicadas nos fins de semana e fora do horário comercial típico para evitar interrupções. Os dispositivos em uma fase serão atualizados gradualmente ao longo de algumas semanas, em vez de todos de uma vez.

Para escolher a fase de atualização automática para seus dispositivos, faça o seguinte:

1. Entre no centro de administração do Microsoft Teams visitando https://admin.teams.microsoft.com.
2. Navegue até **dispositivos do Teams** e selecione **Telefones**, **Exibições**, **Painéis** ou **Salas do Teams no Android**.  
3. Selecione um ou mais dispositivos e selecione **Atualizar**.
4. Em **Atualização automática do Firmware**, selecione um dos seguintes procedimentos:
    - **Teste** Essa opção é melhor para dispositivos de laboratório ou teste nos quais você pode realizar qualquer validação necessária para executar. Atualizações iniciar a implantação assim que a versão mais recente do firmware for lançada. Anteriormente chamado **o mais rápido possível**.
    - **Geral** Essa é a opção padrão e é melhor para a maioria dos seus dispositivos de uso geral. Atualizações iniciar a implantação somente depois de 30 dias ter decorrido da versão do novo firmware. Anteriormente chamado **Defer por 30 dias**.
    - **Final** Essa opção é melhor para dispositivos usados por VIPs e em configurações grandes após a conclusão da validação em larga escala. Atualizações iniciar a implantação somente após 90 dias se passaram da versão do novo firmware. Anteriormente chamado **Defer por 90 dias**.
5. Selecione **Atualizar**.

Para ver em quais dispositivos de fase estão, consulte a coluna **de atualização automática do Firmware** no centro de administração do Teams. Para ver quais dispositivos fazem parte de uma fase específica, use a opção **Filtrar** com o parâmetro **de fase de atualização automática** .

Para reverter uma atualização de firmware de dispositivo, você precisa redefinir seu dispositivo para as configurações de fábrica. Redefina seu dispositivo usando as instruções de seu fabricante.  

## <a name="manually-update-remote-devices"></a>Atualizar dispositivos remotos manualmente

Se você quiser atualizar manualmente dispositivos usando o centro de administração do Teams, poderá decidir se deve atualizar os dispositivos imediatamente ou agendar uma atualização para uma data e hora futuras.

Para atualizar manualmente dispositivos remotos, faça o seguinte:

1. Entre no centro de administração do Microsoft Teams visitando https://admin.teams.microsoft.com.
2. Navegue **por Dispositivos do Teams** e selecione **Telefones**, **Exibições**, **Painéis** ou **Salas do Teams no Android**.
3. Selecione um ou mais dispositivos e selecione **Atualizar**.
4. Em **Atualizações manuais**, **selecione Agendar** se você quiser agendar a atualização para uma data e hora futuras. As atualizações são aplicadas na data e hora no fuso horário selecionado no **Fuso Horário**.

O que você verá depende se você tem um ou vários dispositivos selecionados. A imagem à esquerda abaixo mostra vários dispositivos selecionados enquanto a imagem à direita mostra um único dispositivo selecionado.

:::image type="content" source="../media/device-update-status.png" alt-text="Exibições de dispositivo única e várias no painel de status da atualização do dispositivo.":::

Ao selecionar vários dispositivos, você pode escolher quais tipos de atualização aplicar a cada dispositivo selecionado. Selecione os tipos de atualização que você deseja aplicar e selecione **Atualizar**.

Quando você seleciona um único dispositivo, são mostradas atualizações disponíveis para o dispositivo. Se vários tipos de atualização estiverem disponíveis para o dispositivo, selecione cada tipo de atualização a ser aplicado. Você pode exibir a **versão atual** aplicada no dispositivo e a **nova versão** que será aplicada. Selecione as atualizações que você deseja aplicar e selecione **Atualizar**.

Depois de selecionar **Atualizar**, as atualizações são aplicadas aos seus dispositivos na data e hora selecionadas se você agendou uma atualização. Se você não selecionou uma data e hora futuras, as atualizações serão aplicadas aos seus dispositivos em poucos minutos.
