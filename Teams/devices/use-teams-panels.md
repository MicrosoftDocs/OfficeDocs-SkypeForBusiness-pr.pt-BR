---
title: Como usar dispositivos Microsoft Teams painéis
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
search.appverid: MET150
ms.localizationpriority: medium
description: Este artigo fornece diretrizes sobre como usar dispositivos Teams painéis.
ms.openlocfilehash: 00d2657179e35e2a5e43cbc0665a6d1533ec70d1
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2022
ms.locfileid: "65760903"
---
# <a name="how-to-use-microsoft-teams-panels"></a>Como usar painéis Microsoft Teams dados

Microsoft Teams painéis são dispositivos de exibição digital compactos montados logo fora dos espaços de reunião, normalmente ao lado das entradas. Esses painéis touchscreen são Microsoft Teams dispositivos que fornecem uma visão rápida sobre o espaço de reunião e a reunião agendada. Com os indicadores de LED e tela inicial com codificação de cores vibrantes, você pode determinar se o espaço está disponível ou reservado a uma distância. Você pode usar Teams painéis para reservar um espaço de reunião disponível para uma reunião ad hoc, no local.

Teams os dispositivos de painéis são pré-instalados com Microsoft Teams e exibem detalhes da reunião agendados por meio de Outlook ou Teams calendários.

Este artigo fornece diretrizes para usuários finais e administradores sobre como usar os dispositivos Teams painéis. Ele também fornece respostas para as [perguntas frequentes sobre](#frequently-asked-questions) como usar esses dispositivos.

Para obter uma visão geral dos dispositivos de painéis e as diretrizes sobre como planejar, entregar e gerenciá-los em sua organização, consulte Implantar Microsoft Teams [painéis](teams-panels.md).

Para um início rápido, confira Introdução [painéis Teams dados](https://support.microsoft.com/office/get-started-with-teams-panels-fa5e85d1-7ff3-4f11-b0b0-277e2302c8be).

## <a name="teams-panels-end-user-experience"></a>Teams painéis de experiência do usuário final

Explore a [tela Inicial do](#explore-teams-panels-home-screen) dispositivo Teams painéis para exibir o espaço de reunião e os detalhes da reunião. Ou toque e role no painel de tela sensível ao toque para executar outras ações.

Use seus Teams painéis para:

- [Exibir detalhes e disponibilidade do espaço de reunião, detalhes da reunião, reservas futuras](#explore-teams-panels-home-screen)
- [Reservar um espaço de reunião disponível](#reserve-meeting-spaces-for-ad-hoc-meetings)
- [Relatar um problema](#report-a-problem)
- [Exibir ou atualizar uma configuração de dispositivo](#view-or-update-a-device-setting)

## <a name="explore-teams-panels-home-screen"></a>Explorar Teams tela inicial dos painéis

A tela Inicial é a interface visual principal do dispositivo Teams painéis.  

Na tela Inicial, você pode exibir detalhes do local e da reunião, reservar um espaço, exibir reservas futuras e identificar o status de disponibilidade atual.

A captura de tela a seguir mostra diferentes partes ou blocos Teams tela inicial dos painéis:

:::image type="content" source="../media/panels-home-screen-explanation.png" alt-text="Esta captura de tela exibe diferentes áreas na Teams tela Inicial dos painéis.":::

Consulte a tabela a seguir para obter uma descrição de cada bloco:

Telha | Descrição
:---|:---
**1- Detalhes do espaço de reunião, dia, data e hora atuais** | Exibe a hora atual, o dia, a data e o nome do espaço de reunião. O nome do espaço de reunião é o nome da conta de recurso que entrou nos painéis.
**2- Disponibilidade de espaço de reunião e detalhes da reunião** | Indica a disponibilidade do espaço de reunião e exibe os detalhes da reunião. Consulte [o bloco Disponibilidade do espaço de reunião e detalhes da reunião](#meeting-space-availability-and-meeting-details-tile).
**3 -Próximo Calendário** | Exibe o calendário do espaço de reunião e a disponibilidade por até 24 horas a partir da hora atual. Role para cima ou para baixo para determinar quais intervalos de tempo estão disponíveis e quais são reservados.
**4 Configurações** | Exibe **o Configurações ícone**. Toque nele para relatar um problema ou atualizar as configurações de dispositivo disponíveis.

### <a name="meeting-space-availability-and-meeting-details-tile"></a>Bloco de detalhes da reunião e disponibilidade do espaço de reunião

A aparência desse bloco e seus recursos variam dependendo da disponibilidade do espaço de reunião e do tipo de reserva.

#### <a name="meeting-space-is-reserved-for-a-scheduled-meeting"></a>O espaço de reunião está reservado para uma reunião agendada

O bloco aparece em roxo para um espaço de reunião reservado para uma reunião agendada (agendada por meio de Outlook ou Teams). Ele exibe o título da reunião em texto proeminente, horários de início e término da reunião e o nome do organizador da reunião. Para uma Teams, o logotipo Teams também é exibido. Com os detalhes da reunião exibidos com destaque, os participantes podem confirmar facilmente que estão no espaço de reunião certo, no momento certo e na reunião certa.

:::image type="content" source="../media/panels-right-tile-scheduled-meeting.png" alt-text="Teams tela inicial dos painéis mostrando que o espaço de reunião está reservado para uma reunião agendada.":::

> [!NOTE]
>
> - Depois de agendar uma reunião, pode levar até 90 segundos para que o calendário sincronize e reflita-o na tela dos painéis.
> - Para uma [reunião agendada marcada como particular](https://support.microsoft.com/office/make-an-appointment-or-meeting-private-dc3898f0-22f5-45c6-8cc8-b4d4db84111d)**, a** reunião privada é exibida em vez do título real da reunião.

#### <a name="meeting-space-is-reserved-for-an-ad-hoc-meeting"></a>O espaço de reunião é reservado para uma reunião ad hoc

O bloco aparece em roxo para um espaço de reunião reservado [para uma reunião ad hoc](#reserve-meeting-spaces-for-ad-hoc-meetings). Ele exibe Reservado em **texto proeminente** , juntamente com os horários de início e término da reunião. As reuniões ad hoc são agendadas automaticamente como Teams reuniões, portanto, o logotipo Teams sempre aparece na tela.

:::image type="content" source="../media/panels-right-tile-reserved-adhoc.png" alt-text="Teams tela inicial dos painéis mostrando que o espaço de reunião está reservado para uma reunião ad hoc.":::

#### <a name="meeting-space-is-available"></a>O espaço de reunião está disponível

O bloco aparece em verde para um espaço de reunião disponível. Ele exibe **Disponível em texto proeminente**, e um botão Reserva  também aparece que você pode tocar para reservar o espaço de reunião [para uma reunião ad hoc](#reserve-meeting-spaces-for-ad-hoc-meetings). Você pode verificar o próximo calendário do espaço de reunião (bloco inferior direito) para decidir a hora de término da reunião ad hoc.

:::image type="content" source="../media/panels-right-tile-available-status.png" alt-text="Esta captura de tela mostra como Teams tela inicial dos painéis aparece quando o espaço de reunião está disponível.":::

## <a name="reserve-meeting-spaces-for-ad-hoc-meetings"></a>Reservar espaços de reunião para reuniões ad hoc

Você pode reservar um [espaço de reunião disponível](#meeting-space-is-available) diretamente dos painéis para uma reunião ad hoc. Todas as reuniões ad hoc são agendadas automaticamente como Teams reuniões. No entanto, uma vez reservado, você não pode liberar ou não reservar esse espaço de reunião por meio de painéis. Somente os administradores da conta de recurso do dispositivo podem cancelar a reunião ad hoc (por meio Outlook ou Teams calendário) para cancelar o espaço.

Para reuniões ad hoc reservadas diretamente dos painéis:

- A hora de início é sempre a hora atual e, como tal, você não pode agende-a para uma hora futura.
- A hora de término pode ser até a próxima reunião agendada ou até 24 horas a partir da hora atual, o que for anterior. Verifique o **bloco Calendário Futuro** na tela Inicial para determinar os intervalos de tempo durante os quais o espaço de reunião está disponível ou reservado.

Para reservar um espaço de reunião disponível para uma reunião ad hoc:

1. Na tela Inicial, toque no **botão Reservar** .
    :::image type="content" source="../media/panels-reserve.png" alt-text="Teams tela inicial dos painéis mostrando o botão Reservar.":::
2. Na tela **de reunião Ad hoc** , examine as opções de hora de término disponíveis. Você pode usar as setas para a direita ou para a esquerda para procurar as opções de hora de término disponíveis.

    :::image type="content" source="../media/panels-reserve-endtime.png" alt-text="Tela de reunião ad hoc mostrando os slots de hora de término.":::

    > [!Note]
    >
    > - As opções de hora de término são exibidas em intervalos de 15 minutos de uma hora.
    > - A hora de término assume como padrão o próximo intervalo de 15 minutos, que é pelo menos cinco minutos após a hora atual. Por exemplo, se a hora atual for 13h57, a hora de término padrão será exibida como 14h15 e não 14h. Isso impede que os usuários reservam o espaço por cinco minutos ou menos. Na captura de tela acima, a hora de término padrão é exibida como 14h, que é o próximo intervalo de 15 minutos que é pelo menos cinco minutos após a hora atual (13:53 PM).
    > - Uma exceção à regra acima é quando a hora de início da próxima reunião está dentro de cinco minutos a partir da hora atual. Nesses casos, você pode reservar o espaço até a próxima hora de início da reunião. Por exemplo, se a hora atual for 13:57 e a próxima hora de início da reunião for 14:00, as 14:00 serão exibidas como a única opção de hora de término e você poderá reservar o espaço por três minutos.

3. Toque no intervalo de tempo de término desejado e, em seguida, toque em **Reservar**.

    Uma janela de confirmação é exibida com um emoji polegar para cima, hora de início e término da reunião e nome do espaço de reunião.
    :::image type="content" source="../media/panels-reserve-confirmation.png" alt-text="Mensagem de confirmação de reunião ad hoc.":::
O bloco direito na tela Inicial agora aparece em roxo e exibe o texto Reservado e  o logotipo Teams texto. Isso indica que o espaço de reunião agora está reservado para uma reunião Teams ad hoc.
  
    :::image type="content" source="../media/panels-right-tile-reserved-adhoc.png" alt-text="Tela inicial mostrando que o espaço de reunião está reservado para uma reunião ad hoc.":::

    > [!NOTE]
    > Se o espaço de reunião for uma Microsoft Teams, você poderá participar desta  reunião Teams com a sala de Microsoft Teams ou Surface Hub dispositivos.

### <a name="report-a-problem"></a>Relatar um problema

Para relatar um problema com o dispositivo ou o espaço de reunião, para solicitar uma atualização de recurso ou para fornecer comentários, use o  ícone Configuração na tela Inicial.

1. Toque no **Configurações** de engrenagem na tela inicial.

2. Toque na **opção Relatar um** problema.

    A **tela Enviar Comentários** é exibida em um formato de formulário.
3. Na lista **suspensa Tipo** , selecione o tipo de solicitação.
4. Na lista **suspensa** Problema, selecione a categoria.
5. No campo **de texto** Título, digite o título usando o teclado dos painéis.
6. No campo de texto abaixo **de Título**, digite detalhes adicionais, se necessário.

    > [!NOTE]
    > Não inclua nenhuma informação de identificação pessoal.

7. Examine suas entradas e toque em **Enviar**.

### <a name="view-or-update-a-device-setting"></a>Exibir ou atualizar uma configuração de dispositivo

Há várias configurações de dispositivo, como sobre acessibilidade, reinicialização e política de privacidade que você pode exibir ou atualizar diretamente dos painéis. As configurações de dispositivo disponíveis podem ser diferentes com base no OEM (Fabricante de Equipamento Original) do seu dispositivo. Para obter informações sobre configurações específicas para seu dispositivo, consulte a documentação do OEM.

Para exibir ou atualizar uma configuração de dispositivo:

1. Toque no **Configurações** na tela Inicial.
2. Na tela **Configurações**, toque em **Configurações do dispositivo**.
3. Na tela **Configurações** dispositivo, toque na configuração que você deseja exibir ou atualizar.
4. Siga o prompt na tela para exibir ou atualizar a configuração.

## <a name="teams-panels-admin-experience"></a>Teams de administração de painéis

Se você for o administrador [da painel do Teams](teams-panels.md\#resource-account-provisioning) de recursos, também será o administrador do Aplicativo Painéis no dispositivo. Como administrador do aplicativo **Panels**, você pode executar todas as funções mencionadas na seção de experiência [](#teams-panels-end-user-experience) do usuário final, além de gerenciar as configurações do aplicativo **Panels** no dispositivo.

Os dispositivos de painéis fornecem dois tipos de configurações de administrador. Você deve ser um administrador de dispositivos para acessar as configurações de administrador disponíveis. Os usuários finais não podem acessar essas configurações.

- Administração configurações específicas do dispositivo, como exibição, hora e data, idioma, bluetooth, WiFi e assim por diante. Consulte a documentação do OEM para saber mais sobre essas configurações.
- Administração configurações **específicas do Aplicativo Painéis** em seu dispositivo, como papel de parede e cor do indicador led. Somente um administrador do **Aplicativo Painéis** pode acessar essas configurações. Como **as configurações** do Aplicativo de Painéis estão disponíveis como parte das configurações de administrador, você deve ter credenciais de entrada do administrador para o  dispositivo e o aplicativo Painéis para acessar as configurações do aplicativo Painéis.

> [!NOTE]
> Todas as atualizações das **configurações do Aplicativo de** Painéis feitas por meio do dispositivo são aplicáveis somente a esse dispositivo específico. Essas atualizações não afetarão outros dispositivos de painéis em sua organização. Por exemplo, se você alterar a imagem de papel de parede da  tela inicial das configurações do aplicativo Painéis, a imagem do papel de parede será alterada somente para esse dispositivo específico.

### <a name="access-panels-app-settings"></a>Configurações do aplicativo painéis de acesso

Você pode acessar **as configurações específicas** do aplicativo painéis usando **a opção Configurações aplicativo** painéis nas configurações de administrador. As etapas para acessar o **aplicativo Panels Configurações** podem ser diferentes com base no OEM do seu dispositivo.

Para acessar a **opção Configurações Aplicativo** de Painéis:

1. Toque no **Configurações** na tela Inicial.
2. Na tela **Configurações**, toque em **Configurações do dispositivo**.
3. Toque no **Administração Configurações**.

    > [!NOTE]
    > Dependendo do OEM do seu dispositivo, talvez seja necessário inserir a senha de administrador do dispositivo agora ou após a próxima etapa.

4. Role para baixo para localizar **a opção Configurações** Aplicativo de Painéis. Toque nele.
5. Toque no **botão Configurações painel** na tela direita.
    A tela com as configurações de Aplicativo **de** Painéis disponíveis é exibida.

    :::image type="content" source="../media/panels-app-settings-screen.png" alt-text="Esta captura de tela exibe a tela com as configurações do aplicativo Painéis disponíveis.":::

    Use esta tela para atualizar as seguintes **configurações de Aplicativo de** Painéis para seu dispositivo:

    - [Wallpaper](#update-the-wallpaper)
    - [Indicador led](#change-the-busy-state-led-color)

#### <a name="pair-a-teams-panel-with-a-microsoft-teams-room-on-android"></a>Emparelhar um painel do Teams com uma sala Microsoft Teams no Android

Para emparelhar um painel do Teams e Teams no Android, ambos os dispositivos devem estar conectados à mesma conta de recurso.

No painel do Teams, entre usando suas credenciais de administrador.

1. Vá para **Configurações > aplicativo de Configurações > Administração Configurações > painéis de dispositivos Configurações > reuniões > emparelhamento de dispositivos.**

2. Um código de seis dígitos será exibido no Salas do Teams na Android de exibição da sala. Insira o código no painel de Teams.  

#### <a name="meeting-check-in-and-room-release"></a>Check-in de reunião e liberação da sala

As configurações de check-in e liberação de sala permitem que os usuários façam check-in em uma reunião Teams painéis na sala reservada no início da reunião. Se um usuário não faz check-in dentro de um período definido após a hora de início da reunião, a sala é liberada e fica disponível para reserva de outras pessoas.

Quando Teams painéis é emparelhado com uma sala de Microsoft Teams no Android, as notificações de check-in podem ser habilitadas para aparecer na exibição da frente da sala quando as reuniões são atrasadas.

Para habilitar o check-in e a liberação da sala, consulte [Check-in e liberação de sala Microsoft Teams Painéis](check-in-and-room-release.md).

#### <a name="room-capacity-warning"></a>Aviso de capacidade da sala

Teams painéis que são emparelhados com uma sala Teams no Android podem exibir uma mensagem de aviso quando uma sala de reunião está na capacidade ou acima da capacidade. Para usar esse recurso, a sala Teams deve ter uma câmera que dê suporte à contagem de pessoas. Salas do Teams em Android suporte a avisos de capacidade de sala sem um painel do Teams.

Os avisos de capacidade da sala são desativados por padrão. Para ativar a configuração do painel do Teams, primeiro emparelhe um painel do Teams com uma sala [Microsoft Teams no Android](#pair-a-teams-panel-with-a-microsoft-teams-room-on-android). O painel e a Teams room devem ser conectados à mesma conta de recurso.

 Em seguida, vá para **Configurações > configurações do dispositivo > Administração configurações > do aplicativo Painel**. Em Seguida, **em Reuniões**, ative **a notificação de ocupação máxima da sala**.

#### <a name="view-room-equipment"></a>Exibir equipamento de sala

Quando esse recurso está ativado, os usuários finais podem exibir quais equipamentos estão disponíveis em um espaço em um painel do Teams.

Esse recurso está desativado por padrão e pode ser habilitado por dispositivo. Para ativá-lo, use [Set-Place](/powershell/module/exchange/set-place?view=exchange-ps) no PowerShell para configurar `AudioDeviceName`os nomes de exibição para , `DisplayDeviceName`, `VideoDeviceName`, `Tags`e `IsWheelChairAccessible`.

Ou você pode habilitar esse recurso no Exchange de administração. Consulte [Editar um recurso](/exchange/recipients-in-exchange-online/manage-resource-mailboxes#edit-a-resource) para obter mais informações.



#### <a name="update-the-wallpaper"></a>Atualizar o papel de parede

Altere a imagem de papel de parede da tela inicial.

1. [Aplicativo **de Painéis de Acesso Configurações**](#access-panels-app-settings).
2. Toque **em Papéis de Parede**.
3. Em **Escolher sua imagem**, selecione uma imagem para definir como a imagem de plano de fundo da tela inicial. Visualize a imagem selecionada em Plano de **Fundo**.
:::image type="content" source="../media/panels-wallpapers-setting.png" alt-text="Esta captura de tela exibe a tela de configurações do papel de parede.":::
4. Voltar tela inicial e verifique se o papel de parede está atualizado.

#### <a name="change-the-busy-state-led-color"></a>Alterar a cor do LED de estado ocupado

Os administradores podem escolher vermelho ou roxo como a cor led para indicar que o espaço de reunião está ocupado ou reservado. A cor do LED para indicar que um espaço disponível é sempre verde e não pode ser alterada.

1. [Aplicativo **de Painéis de Acesso Configurações**](#access-panels-app-settings).
2. Toque **em LED Configurações**.
3. Em **Escolher a cor do LED**, selecione a cor desejada.
:::image type="content" source="../media/panels-led-settings.png" alt-text="Esta captura de tela exibe as configurações de estado ocupado da cor do LED.":::
4. Voltar na tela inicial e verifique se a cor do LED para o estado ocupado está atualizada. Se o espaço de reunião estiver disponível no momento, tente agendar uma reunião de teste para verificar a alteração na cor do LED para o estado ocupado.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

Encontre respostas para perguntas frequentes sobre os dispositivos Teams painéis.

**Até que ponto no futuro posso ver os detalhes de agendamento de um espaço de reunião?**  
No bloco **Calendário** futuro (inferior direito) na tela Inicial, você pode ver os detalhes de agendamento de um espaço de reunião por até 24 horas no futuro a partir da hora atual.

**Posso reservar um espaço de reunião por um tempo futuro no dispositivo Teams painéis?**  
Não, você não pode reservar um espaço de reunião para uma hora futura dos painéis. A hora de início é sempre a hora atual de uma reunião ad hoc agendada nos painéis.

**Por quanto tempo posso reservar um espaço de reunião disponível para uma reunião ad hoc?**  
Você pode reservar um espaço de reunião disponível a partir da hora atual até a próxima hora de reunião agendada ou até um máximo de 24 horas a partir da hora atual, o que for anterior. Por exemplo, se a hora atual for 10h e a próxima hora de início da reunião for 14h, você poderá reservar o espaço de reunião das 10h às 14h.
