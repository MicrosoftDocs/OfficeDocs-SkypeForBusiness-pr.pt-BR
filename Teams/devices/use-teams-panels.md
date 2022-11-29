---
title: Como usar Microsoft dispositivos de painéis do Teams
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: weizxue
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
- Teams_ITAdmin_Devices
search.appverid: MET150
ms.localizationpriority: medium
description: Este artigo fornece diretrizes sobre como usar dispositivos de painéis do Teams.
ms.openlocfilehash: b5dbe92b1c2c3f08683ca58a403fdbb4e318efca
ms.sourcegitcommit: 75b29de261b4de652c7f2e89da4ad7158da773f1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/29/2022
ms.locfileid: "69183000"
---
# <a name="how-to-use-microsoft-teams-panels"></a>Como usar painéis do Microsoft Teams

Microsoft painéis do Teams são dispositivos de exibição digital compactos que são montados fora dos espaços de reunião, normalmente ao lado de entradas. Esses painéis touchscreen são dedicados Microsoft dispositivos do Teams que fornecem uma visão detalhada sobre o espaço de reunião e a reunião agendada. Com os indicadores de led e tela inicial codificados por cores vibrantes, você pode determinar se o espaço está disponível ou reservado à distância. Você pode usar painéis do Teams para reservar um espaço de reunião disponível para uma reunião ad hoc, no local.

Os dispositivos de painéis do Teams vêm pré-instalados com Microsoft Teams e exibem detalhes da reunião agendados por meio de calendários do Outlook ou do Teams.

Este artigo fornece diretrizes, para usuários finais e administradores, sobre como usar os dispositivos de painéis do Teams. Ele também fornece respostas para as [perguntas frequentes](#frequently-asked-questions) sobre o uso desses dispositivos.

Para obter uma visão geral dos dispositivos de painéis e as diretrizes sobre como planejar, entregar e gerenciá-los em sua organização, consulte [Implantar Microsoft painéis do Teams](teams-panels.md).

Para um início rápido, confira [Introdução aos painéis do Teams](https://support.microsoft.com/office/get-started-with-teams-panels-fa5e85d1-7ff3-4f11-b0b0-277e2302c8be).

## <a name="teams-panels-end-user-experience"></a>Experiência de usuário final dos painéis do Teams

Explore a [tela inicial](#explore-teams-panels-home-screen) do dispositivo de painéis do Teams para exibir o espaço de reunião e os detalhes da reunião. Ou toque e role no painel touchscreen para fazer outras ações.

Use seus dispositivos de painéis do Teams para:

- [Exibir detalhes e disponibilidade do espaço de reunião, detalhes da reunião, reservas futuras](#explore-teams-panels-home-screen)
- [Reservar um espaço de reunião disponível](#reserve-meeting-spaces-for-ad-hoc-meetings)
- [Relatar um problema](#report-a-problem)
- [Exibir ou atualizar uma configuração de dispositivo](#view-or-update-a-device-setting)

## <a name="explore-teams-panels-home-screen"></a>Explorar painéis do Teams Tela inicial

A tela inicial é a interface visual principal do dispositivo de painéis do Teams.  

Na tela Inicial, você pode exibir detalhes de localização e reunião, reservar um espaço, exibir reservas futuras e identificar o status de disponibilidade atual.

A captura de tela a seguir mostra diferentes partes ou blocos nos painéis do Teams Tela inicial:

:::image type="content" source="../media/panels-home-screen-explanation.png" alt-text="Esta captura de tela exibe diferentes áreas na tela inicial dos painéis do Teams.":::

Consulte a tabela a seguir para obter uma descrição de cada bloco:

Telha | Descrição
:---|:---
**1-Detalhes de horário, dia, data e espaço de reunião atuais** | Exibe a hora, o dia, a data e o nome do espaço de reunião atuais. O nome do espaço de reunião é o nome da conta de recurso que entrou nos painéis.
**2- Disponibilidade de espaço de reunião e detalhes da reunião** | Indica a disponibilidade do espaço de reunião e exibe detalhes da reunião. Consulte [Disponibilidade de espaço de reunião e bloco de detalhes da reunião](#meeting-space-availability-and-meeting-details-tile).
**Calendário de 3 próximos** | Exibe o calendário e a disponibilidade do espaço de reunião por até 24 horas a partir da hora atual. Role para cima ou para baixo para determinar quais slots de tempo estão disponíveis e quais são reservados.
**4 configurações** | Exibe o ícone **Configurações** . Toque nele para relatar um problema ou atualizar as configurações de dispositivo disponíveis.

### <a name="meeting-space-availability-and-meeting-details-tile"></a>Bloco de detalhes da reunião e disponibilidade do espaço de reunião

A aparência desse bloco e suas funcionalidades variam dependendo da disponibilidade do espaço de reunião e do tipo de reserva.

#### <a name="meeting-space-is-reserved-for-a-scheduled-meeting"></a>O espaço de reunião está reservado para uma reunião agendada

O bloco aparece em roxo para um espaço de reunião reservado para uma reunião agendada (agendada via Outlook ou Teams). Ele exibe o título da reunião em texto proeminente, horários de início e término da reunião e o nome do organizador da reunião. Para uma reunião do Teams, o logotipo do Teams também é exibido. Com os detalhes da reunião exibidos com destaque, os participantes podem confirmar facilmente que estão no espaço de reunião certo, na hora certa e para a reunião certa.

:::image type="content" source="../media/panels-right-tile-scheduled-meeting.png" alt-text="Painéis do Teams Tela inicial mostrando que o espaço de reunião está reservado para uma reunião agendada.":::

> [!NOTE]
>
> - Depois de agendar uma reunião, pode levar até 90 segundos para o calendário sincronizar e refleti-la na tela de painéis.
> - Para uma [reunião agendada marcada como privada](https://support.microsoft.com/office/make-an-appointment-or-meeting-private-dc3898f0-22f5-45c6-8cc8-b4d4db84111d), **a reunião privada** é exibida em vez do título da reunião real.

#### <a name="meeting-space-is-reserved-for-an-ad-hoc-meeting"></a>O espaço de reunião é reservado para uma reunião ad hoc

O bloco aparece em roxo para um espaço de reunião [reservado para uma reunião ad hoc](#reserve-meeting-spaces-for-ad-hoc-meetings). Ele exibe **Reservado em** texto proeminente junto com os horários de início e término da reunião. As reuniões Ad-hoc são agendadas automaticamente como reuniões do Teams, portanto, o logotipo do Teams sempre aparece na tela.

:::image type="content" source="../media/panels-right-tile-reserved-adhoc.png" alt-text="Painéis do Teams Tela inicial mostrando que o espaço de reunião está reservado para uma reunião ad hoc.":::

#### <a name="meeting-space-is-available"></a>O espaço de reunião está disponível

O bloco aparece em verde para um espaço de reunião disponível. Ele é exibido **disponível** em texto proeminente e um botão **Reserva** também aparece que você pode tocar para [reservar o espaço de reunião para uma reunião ad hoc](#reserve-meeting-spaces-for-ad-hoc-meetings). Você pode verificar o próximo calendário do espaço de reunião (bloco inferior direito) para decidir a hora de término da reunião ad hoc.

:::image type="content" source="../media/panels-right-tile-available-status.png" alt-text="Esta captura de tela mostra como a tela inicial dos painéis do Teams é exibida quando o espaço de reunião está disponível.":::

## <a name="reserve-meeting-spaces-for-ad-hoc-meetings"></a>Reservar espaços de reunião para reuniões ad hoc

Você pode reservar um [espaço de reunião disponível](#meeting-space-is-available) diretamente dos painéis para uma reunião ad hoc. Todas as reuniões ad hoc são agendadas automaticamente como reuniões do Teams. No entanto, uma vez reservado, você não pode liberar ou cancelar esse espaço de reunião por meio de painéis. Somente os administradores da conta de recursos do dispositivo podem cancelar a reunião ad hoc (via outlook ou calendário do Teams) para cancelar a reserva do espaço.

Para reuniões ad hoc reservadas diretamente dos painéis:

- A hora de início é sempre a hora atual e, como tal, você não pode agende-a para uma hora futura.
- O horário de término pode ser até a próxima reunião agendada ou até 24 horas a partir da hora atual, o que for anterior. Verifique o **próximo bloco Calendário** na tela Inicial para determinar os slots de tempo durante os quais o espaço de reunião está disponível ou reservado.

Para reservar um espaço de reunião disponível para uma reunião ad hoc:

1. Na tela Inicial, toque no botão **Reservar** .
    :::image type="content" source="../media/panels-reserve.png" alt-text="Painéis do Teams Tela inicial mostrando o botão Reservar.":::
2. Na tela **de reunião do Ad hoc** , examine as opções de hora de término disponíveis. Você pode usar as setas para a direita ou para a esquerda para navegar pelas opções de hora de término disponíveis.

    :::image type="content" source="../media/panels-reserve-endtime.png" alt-text="Tela de reunião ad hoc mostrando slots de hora de término.":::

    > [!Note]
    >
    > - As opções de hora de término são exibidas em intervalos de 15 minutos de uma hora.
    > - O tempo de término é padrão para o próximo intervalo de 15 minutos que é pelo menos cinco minutos após o tempo atual. Por exemplo, se a hora atual for 13h57, o horário de término padrão será exibido como 14h15 e não às 14h. Isso impede que os usuários reservam o espaço por cinco minutos ou menos. Na captura de tela acima, o horário de término padrão é exibido como 14:00, que é o próximo intervalo de 15 minutos que é pelo menos cinco minutos após o horário atual (13:53 PM).
    > - Uma exceção à regra acima é quando a hora de início da próxima reunião é dentro de cinco minutos a partir do momento atual. Nesses casos, você pode reservar o espaço até a próxima hora de início da reunião. Por exemplo, se a hora atual for 13h57 e a próxima hora de início da reunião for às 14h, as 14h serão exibidas como a única opção de hora de término e você poderá reservar o espaço por três minutos.

3. Toque no intervalo de tempo de término desejado e toque em **Reservar**.

    Uma janela de confirmação é exibida com um emoji de polegar para cima, início e hora de término da reunião e nome do espaço de reunião.
    :::image type="content" source="../media/panels-reserve-confirmation.png" alt-text="Mensagem de confirmação da reunião ad hoc.":::
O bloco direito na tela Inicial agora aparece em roxo e exibe o texto **Reservado** e o logotipo do Teams. Isso indica que o espaço de reunião agora está reservado para uma reunião do Teams ad hoc.
  
    :::image type="content" source="../media/panels-right-tile-reserved-adhoc.png" alt-text="Tela inicial mostrando que o espaço de reunião está reservado para uma reunião ad hoc.":::

    > [!NOTE]
    > Se o espaço de reunião for um Microsoft Sala do Teams, você poderá _participar_ desta reunião do Teams com os dispositivos Microsoft Sala do Teams ou Surface Hub.

### <a name="report-a-problem"></a>Relatar um problema

Para relatar um problema com o dispositivo ou o espaço de reunião, para solicitar uma atualização de recurso ou para fornecer qualquer comentário, use o ícone **Configuração** na tela Inicial.

1. Toque no ícone **De configurações** de engrenagem na tela Inicial.

2. Toque na opção **Relatar um problema** .

    A tela **Enviar Comentários** é exibida em um formato de formulário.
3. Na lista suspensa **Tipo** , selecione o tipo de solicitação.
4. Na lista suspensa **Problema** , selecione a categoria.
5. No campo **texto Título** , digite o título usando o teclado de painéis.
6. No campo de texto abaixo **de Título**, digite detalhes adicionais, se necessário.

    > [!NOTE]
    > Não inclua nenhuma informação identificável pessoalmente.

7. Examine suas entradas e toque em **Enviar**.

### <a name="view-or-update-a-device-setting"></a>Exibir ou atualizar uma configuração de dispositivo

Há várias configurações de dispositivo, como sobre, acessibilidade, reinicialização e política de privacidade que você pode exibir ou atualizar diretamente dos painéis. As configurações de dispositivo disponíveis podem ser diferentes com base no OEM (Fabricante de Equipamento Original) do seu dispositivo. Para obter informações sobre configurações específicas do dispositivo, consulte a documentação do OEM.

Para exibir ou atualizar uma configuração de dispositivo:

1. Toque no ícone **Configurações** na tela Inicial.
2. Na tela **Configurações** , toque em **Configurações do dispositivo**.
3. Na tela **Configurações do Dispositivo** , toque na configuração que você deseja exibir ou atualizar.
4. Siga o prompt na tela para exibir ou atualizar a configuração.

## <a name="teams-panels-admin-experience"></a>Experiência de administrador de painéis do Teams

Se você for o administrador da [conta de recursos do painel do Teams](teams-panels.md\#resource-account-provisioning), também será o administrador do **Aplicativo de Painéis** no dispositivo. Como administrador do **Aplicativo de Painéis** , você pode fazer todas as funções mencionadas na seção [experiência do usuário final](#teams-panels-end-user-experience) , além de gerenciar as configurações do **Aplicativo painéis** no dispositivo.

Os dispositivos de painéis fornecem dois tipos de configurações de administrador. Você deve ser um administrador de dispositivo para acessar as configurações de administrador disponíveis. Os usuários finais não podem acessar essas configurações.

- Administração configurações específicas para o dispositivo, como exibição, hora e data, idioma, bluetooth, WiFi e assim por diante. Consulte a documentação do OEM para saber mais sobre essas configurações.
- Administração configurações específicas do **Aplicativo Painéis** em seu dispositivo, como papel de parede e cor do indicador LED. Somente um administrador do **Aplicativo de Painéis** pode acessar essas configurações. Como as configurações de **aplicativo de painéis** estão disponíveis como parte das configurações de administrador, você deve ter credenciais de logon de administrador para o dispositivo e o **Aplicativo de Painéis** acessar as configurações **do aplicativo Panels** .

> [!NOTE]
> Todas as atualizações para as configurações do **Aplicativo de Painéis feitas** por meio do dispositivo são aplicáveis somente a esse dispositivo específico. Essas atualizações não afetarão outros dispositivos de painéis em sua organização. Por exemplo, se você alterar a imagem de papel de parede da tela inicial das configurações do **Aplicativo Painéis** , a imagem de papel de parede será alterada apenas para esse dispositivo específico.

### <a name="access-panels-app-settings"></a>Configurações do aplicativo Painéis de Acesso

Você pode acessar **configurações específicas do aplicativo de painéis** usando a opção **Configurações de administrador do Teams** nas configurações de administrador. As etapas para acessar **as configurações de administrador do Teams** podem ser diferentes com base no OEM do seu dispositivo.

Para acessar a opção **configurações de administrador do Teams** :

1. Toque no ícone **Configurações** na tela Inicial.
2. Na tela **Configurações** , toque em **Configurações do dispositivo**.

    > [!NOTE]
    > Dependendo do OEM do dispositivo, talvez seja necessário inserir a senha de administrador do dispositivo agora ou após a próxima etapa.

3. Role para baixo para encontrar a opção **configurações de administrador do Teams** . Toque nele.

> [!NOTE]
> Alguns OEMs podem substituir a opção **configurações de administrador do Teams** por sua própria opção personalizada. Se você não vir a opção **configurações de administrador do Teams** , verifique a documentação do dispositivo para obter instruções sobre como acessar as configurações de administrador do painel.

#### <a name="pair-a-teams-panel-with-a-microsoft-teams-room-on-android"></a>Emparelhar um painel do Teams com uma sala do Teams Microsoft no Android

Para emparelhar um painel do Teams e o Teams Room no Android, ambos os dispositivos devem ser conectados à mesma conta de recursos.

No painel do Teams, entre usando suas credenciais de administrador.

1. Acesse **Configurações > Configurações do dispositivo > configurações de administrador do Teams > emparelhamento de dispositivo.**

2. Um código de seis dígitos será exibido no Salas do Teams na frente do Android da exibição da sala. Insira o código no Painel do Teams.  

#### <a name="enable-or-disable-meeting-check-in-and-automatic-room-release"></a>Habilitar ou desabilitar o check-in de reunião e a versão automática da sala

As configurações de entrada e de versão da sala permitem que os usuários entrem em uma reunião nos Painéis do Teams na sala reservada no início da reunião. Se um usuário não fizer check-in dentro de um tempo definido após o horário de início da reunião, a sala será liberada e ficará disponível para outras pessoas reservarem.

Quando os Painéis do Teams são emparelhados com um Microsoft Sala do Teams no Android, as notificações de check-in podem ser habilitadas para aparecer na tela frontal da sala quando as reuniões forem executadas com atraso.

Para habilitar a liberação do check-in e da sala, consulte [Entrada e liberação de sala em Microsoft Painéis do Teams](check-in-and-room-release.md).

#### <a name="enable-or-disable-check-out-manual-room-release"></a>Habilitar ou desabilitar o check-out (versão manual da sala)

Quando o check-out está habilitado, os usuários finais podem usar um painel do Teams para liberar manualmente uma sala. A liberação de uma sala encerra a reserva atual e disponibiliza a sala para outras pessoas agendarem.

Esse recurso está desabilitado por padrão, mas pode ser habilitado por dispositivo. Para habilitar o recurso, acesse **Configurações > Configurações do dispositivo > configurações de administrador do Teams > Reuniões** e ative **Check-out**.

> [!NOTE]
> Se uma sala for liberada antes do fim de uma reserva agendada, o organizador receberá uma mensagem de email da sala recusando-a. Isso acontece porque a sala remove a reserva de sua agenda para que ela possa ser reservada por outros usuários. A mensagem que recusa a reserva pode ser ignorada.

> [!NOTE]
> Um painel do Teams não pode ser usado para liberar uma sala se o dispositivo Salas do Teams com o qual ele está emparelhado estiver em uma chamada ativa.

#### <a name="enable-or-disable-room-reservations"></a>Habilitar ou desabilitar reservas de sala

Quando as reservas de sala estão habilitadas, os usuários finais podem usar uma painel do Teams para reservar uma sala que está disponível no momento. As reservas começam no momento em que o botão **Reserva** é tocado e sua duração pode ser aumentada em incrementos de 15 minutos até o horário de início da próxima reserva ou para um máximo de 24 horas.

Esse recurso está habilitado por padrão, mas pode ser desabilitado por dispositivo. Para desabilitar o recurso, acesse **Configurações > Configurações do dispositivo > configurações de administrador do Teams > Reuniões** e ative **Desabilitar reservas de sala**.

#### <a name="enable-or-disable-extension-of-existing-room-reservations"></a>Habilitar ou desabilitar a extensão das reservas de sala existentes

Quando as extensões de reserva de sala estiverem habilitadas, os usuários finais poderão usar uma painel do Teams para estender a reserva existente de uma sala se a sala estiver disponível após o horário de término original da reserva. As reservas podem ser estendidas em incrementos de 15 minutos até o horário de início da próxima reunião ou para um máximo de 24 horas no futuro, o que for mais cedo.

Esse recurso está desabilitado por padrão, mas pode ser habilitado por dispositivo. Para habilitar o recurso, acesse **Configurações > Configurações do dispositivo > configurações de administrador do Teams > Reuniões** e ative **Estender reserva de sala**.

#### <a name="enable-or-disable-room-capacity-warnings"></a>Habilitar ou desabilitar avisos de capacidade de sala

Os painéis do Teams emparelhados com uma Sala do Teams no Android podem exibir uma mensagem de aviso quando uma sala está em ou acima da capacidade. Para usar esse recurso, a Sala do Teams deve ter uma câmera que dê suporte à contagem de pessoas. Salas do Teams em avisos de capacidade da sala de suporte do Android sem um painel do Teams.

Os avisos de capacidade da sala são desabilitados por padrão, mas podem ser habilitados por dispositivo. Para habilitar o recurso, faça o seguinte:

1. Siga as etapas em [Emparelhar um painel do Teams com um Microsoft Sala do Teams no Android](#pair-a-teams-panel-with-a-microsoft-teams-room-on-android). O painel e o dispositivo do Teams Room devem ser conectados à mesma conta de recurso.
2. Acesse **Configurações > Configurações do dispositivo > configurações de administrador do Teams > Reuniões** e ative a **notificação de ocupação da sala Max**.

#### <a name="enable-or-disable-viewing-of-room-equipment"></a>Habilitar ou desabilitar a exibição de equipamentos de sala

Quando esse recurso é ativado, os usuários finais podem exibir quais equipamentos estão disponíveis em um espaço em um painel do Teams.

Esse recurso está desativado por padrão e pode ser habilitado por dispositivo. Para ativá-lo, use [Set-Place](/powershell/module/exchange/set-place) no PowerShell para configurar os nomes de exibição para `AudioDeviceName`, `DisplayDeviceName`, `VideoDeviceName`, `Tags`e `IsWheelChairAccessible`.

Ou você pode habilitar esse recurso no centro de administração do Exchange. Consulte [Editar um recurso](/exchange/recipients-in-exchange-online/manage-resource-mailboxes#edit-a-resource) para obter mais informações.

#### <a name="update-the-wallpaper"></a>Atualizar o papel de parede

Altere a imagem de papel de parede da tela inicial.

1. [Acessar **as configurações de administrador do Teams**](#access-panels-app-settings).
2. Toque **em Papéis de Parede**.
3. Em **Escolher sua imagem**, selecione uma imagem para definir como a imagem de fundo da tela inicial. Visualizar a imagem selecionada em **Plano de Fundo**.
:::image type="content" source="../media/panels-wallpapers-setting.png" alt-text="Esta captura de tela exibe a tela de configurações do papel de parede.":::
4. Voltar para a tela Inicial e verifique se o papel de parede está atualizado.

#### <a name="change-the-busy-state-led-color"></a>Alterar a cor led de estado ocupado

Os administradores podem escolher vermelho ou roxo como a cor LED para indicar que o espaço de reunião está ocupado ou reservado. A cor led para indicar um espaço disponível é sempre verde e não pode ser alterada.

1. [Acessar **as configurações de administrador do Teams**](#access-panels-app-settings).
2. Toque **em Configurações de LED**.
3. Em **Escolher sua cor DE LED**, selecione a cor desejada.
:::image type="content" source="../media/panels-led-settings.png" alt-text="Esta captura de tela exibe as configurações de estado ocupado de cor LED.":::
4. Voltar para a tela Inicial e verifique se a cor LED do estado ocupado está atualizada. Se o espaço de reunião estiver disponível no momento, tente agendar uma reunião de teste para verificar a alteração na cor do LED para o estado ocupado.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

Encontre respostas para perguntas frequentes sobre os dispositivos de painéis do Teams.

**Até onde no futuro posso ver os detalhes de agendamento de um espaço de reunião?**  
No **próximo bloco Calendário** (inferior direito) na tela Inicial, você pode ver os detalhes de agendamento de um espaço de reunião por até 24 horas no futuro a partir da hora atual.

**Posso reservar um espaço de reunião para um tempo futuro no dispositivo de painéis do Teams?**  
Não, você não pode reservar um espaço de reunião para um tempo futuro dos painéis. A hora de início é sempre a hora atual para uma reunião ad hoc agendada dos painéis.

**Quanto tempo posso reservar um espaço de reunião disponível para uma reunião ad hoc?**  
Você pode reservar um espaço de reunião disponível a partir do horário atual até a próxima hora de reunião agendada ou até um máximo de 24 horas a partir da hora atual, o que for anterior. Por exemplo, se a hora atual for 10h e a próxima hora de início da reunião for 14h, você poderá reservar o espaço de reunião das 10h às 14h.
