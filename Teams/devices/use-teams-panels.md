---
title: Como usar Microsoft Teams painéis
ms.author: czawideh
author: cazawideh
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
description: Este artigo fornece orientações sobre como usar dispositivos Teams painéis.
---

# <a name="how-to-use-microsoft-teams-panels"></a>Como usar Microsoft Teams painéis

Microsoft Teams painéis são dispositivos de exibição digital compactos que são montados fora dos espaços de reunião, normalmente ao lado de entradas. Esses painéis touchscreen são Microsoft Teams dispositivos que fornecem uma visão geral sobre o espaço de reunião e a reunião agendada. Com os indicadores de LED e tela inicial codificados por cores vibrantes, você pode determinar se o espaço está disponível ou reservado de uma distância. Você pode usar Teams painéis para reservar um espaço de reunião disponível para uma reunião ad hoc, no local.

Teams painéis são pré-instalados com Microsoft Teams e exibem detalhes da reunião agendados por meio de calendários Outlook ou Teams.

Este artigo fornece orientações, para usuários finais e administradores, sobre como usar os dispositivos de Teams painéis. Ele também fornece respostas às [perguntas frequentes sobre](#frequently-asked-questions) como usar esses dispositivos.

Para obter uma visão geral dos dispositivos de painéis e as diretrizes sobre como planejar, entregar e gerenciá-los em sua organização, consulte [Deploy Microsoft Teams panels](teams-panels.md).

Para um início rápido, confira Introdução [com Teams painéis](https://support.microsoft.com/office/get-started-with-teams-panels-fa5e85d1-7ff3-4f11-b0b0-277e2302c8be).

## <a name="teams-panels-end-user-experience"></a>Teams painéis experiência do usuário final

Explore a [tela inicial do](#explore-teams-panels-home-screen) seu dispositivo Teams painéis para exibir o espaço de reunião e os detalhes da reunião. Ou toque e role no painel touchscreen para fazer outras ações.

Use seus Teams painéis para:

- [Exibir detalhes do espaço de reunião e disponibilidade, detalhes da reunião, reservas futuras](#explore-teams-panels-home-screen)
- [Reservar um espaço de reunião disponível](#reserve-meeting-spaces-for-ad-hoc-meetings)
- [Relatar um problema](#report-a-problem)
- [Exibir ou atualizar uma configuração de dispositivo](#view-or-update-a-device-setting)

## <a name="explore-teams-panels-home-screen"></a>Explorar Teams tela inicial dos painéis

A tela inicial é a interface visual principal do dispositivo Teams painéis.  

Na tela Inicial, você pode exibir detalhes de local e reunião, reservar um espaço, exibir reservas futuras e identificar o status de disponibilidade atual.

A captura de tela a seguir mostra diferentes partes ou blocos na tela inicial Teams painéis:

:::image type="content" source="../media/panels-home-screen-explanation.png" alt-text="Esta captura de tela exibe diferentes áreas na tela inicial Teams painéis.":::

Consulte a tabela a seguir para uma descrição de cada telha:

Tile | Descrição
:---|:---
**1-Detalhes do espaço de reunião, dia, data e hora atuais** | Exibe a hora atual, o dia, a data e o nome do espaço de reunião. O nome do espaço de reunião é o nome da conta de recurso que se inscreveu nos painéis.
**2-Disponibilidade de espaço de reunião e detalhes da reunião** | Indica a disponibilidade do espaço de reunião e exibe os detalhes da reunião. Confira [Disponibilidade de espaço de reunião e o tile de detalhes da reunião](#meeting-space-availability-and-meeting-details-tile).
**Calendário 3-Futuro** | Exibe o calendário e a disponibilidade do espaço de reunião por até 24 horas a partir da hora atual. Role para cima ou para baixo para determinar quais intervalos de tempo estão disponíveis e quais são reservados.
**4 Configurações** | Exibe **o Configurações ícone**. Toque nele para relatar um problema ou atualizar as configurações de dispositivo disponíveis.

### <a name="meeting-space-availability-and-meeting-details-tile"></a>Espaço de reunião e o tile de detalhes da reunião

A aparência desse telha e seus recursos variam dependendo da disponibilidade do espaço de reunião e do tipo de reserva.

#### <a name="meeting-space-is-reserved-for-a-scheduled-meeting"></a>O espaço de reunião é reservado para uma reunião agendada

O azulejo aparece em roxo para um espaço de reunião reservado para uma reunião agendada (agendada por meio de Outlook ou Teams). Ele exibe o título da reunião em texto proeminente, horários de início e término da reunião e o nome do organizador da reunião. Para uma Teams, o logotipo Teams também é exibido. Com os detalhes da reunião exibidos com destaque, os participantes podem confirmar facilmente que estão no espaço de reunião certo, no momento certo e na reunião certa.

:::image type="content" source="../media/panels-right-tile-scheduled-meeting.png" alt-text="Teams tela inicial dos painéis mostrando que o espaço de reunião está reservado para uma reunião agendada.":::

> [!NOTE]
>
> - Depois de agendar uma reunião, pode levar até 90 segundos para que o calendário sincronize e reflita na tela de painéis.
> - Para uma [reunião agendada marcada como privada](https://support.microsoft.com/office/make-an-appointment-or-meeting-private-dc3898f0-22f5-45c6-8cc8-b4d4db84111d), **a reunião** privada é exibida em vez do título real da reunião.

#### <a name="meeting-space-is-reserved-for-an-ad-hoc-meeting"></a>O espaço de reunião é reservado para uma reunião ad hoc

O azulejo aparece em roxo para um espaço de reunião reservado [para uma reunião ad hoc](#reserve-meeting-spaces-for-ad-hoc-meetings). Ele exibe **Reservado em texto** proeminente juntamente com os horários de início e término da reunião. As reuniões ad hoc são agendadas automaticamente como reuniões Teams, portanto, o logotipo Teams sempre aparece na tela.

:::image type="content" source="../media/panels-right-tile-reserved-adhoc.png" alt-text="Teams tela inicial dos painéis mostrando que o espaço de reunião está reservado para uma reunião ad hoc.":::

#### <a name="meeting-space-is-available"></a>O espaço de reunião está disponível

O azulejo aparece em verde para um espaço de reunião disponível. Ele exibe **Available em** texto proeminente, e um botão **Reserva** também aparece que você pode tocar para reservar o espaço de reunião para uma reunião [ad hoc](#reserve-meeting-spaces-for-ad-hoc-meetings). Você pode verificar o próximo calendário do espaço de reunião (azulejo inferior direito) para decidir a hora de término da reunião ad hoc.

:::image type="content" source="../media/panels-right-tile-available-status.png" alt-text="Esta captura de tela mostra como Teams tela inicial dos painéis aparece quando o espaço de reunião está disponível.":::

## <a name="reserve-meeting-spaces-for-ad-hoc-meetings"></a>Reservar espaços de reunião para reuniões ad hoc

Você pode reservar [um espaço de reunião disponível](#meeting-space-is-available) diretamente de painéis para uma reunião ad hoc. Todas as reuniões ad hoc são agendadas automaticamente como Teams reuniões. No entanto, uma vez reservado, você não pode liberar ou não reservar esse espaço de reunião por meio de painéis. Somente os administradores da conta de recurso do dispositivo podem cancelar a reunião ad hoc (por meio Outlook ou Teams calendário) para não reservar o espaço.

Para reuniões ad hoc reservadas diretamente de painéis:

- A hora de início é sempre a hora atual e, como tal, você não pode agende-la para uma hora futura.
- A hora de término pode ser até a próxima reunião agendada ou até 24 horas a partir da hora atual, o que for anterior. Verifique o **bloqueio Calendário Futuro** na tela Inicial para determinar os intervalos de tempo durante os quais o espaço de reunião está disponível ou reservado.

Para reservar um espaço de reunião disponível para uma reunião ad hoc:

1. Na tela Inicial, toque no **botão Reserva** .
    :::image type="content" source="../media/panels-reserve.png" alt-text="Teams tela inicial dos painéis mostrando o botão Reserva.":::
2. Na tela **de reunião Ad hoc** , revise as opções de hora de término disponíveis. Você pode usar as setas direita ou esquerda para procurar as opções de hora de término disponíveis.

    :::image type="content" source="../media/panels-reserve-endtime.png" alt-text="Tela de reunião ad hoc mostrando intervalos de tempo de término.":::

    > [!Note]
    >
    > - As opções de hora final são exibidas em intervalos de 15 minutos de uma hora.
    > - A hora de término é padrão para o próximo intervalo de 15 minutos que é pelo menos cinco minutos após a hora atual. Por exemplo, se a hora atual for 13:57, a hora de término padrão será exibida como 14:15 e não 14:00. Isso impede que os usuários reservem o espaço por cinco minutos ou menos. Na captura de tela acima, a hora de término padrão é exibida como 14:00 PM, que é o próximo intervalo de 15 minutos que é pelo menos cinco minutos após a hora atual (13:53 PM).
    > - Uma exceção à regra acima é quando a hora de início da próxima reunião está dentro de cinco minutos a partir da hora atual. Nesses casos, você pode reservar o espaço até a próxima hora de início da reunião. Por exemplo, se a hora atual for 13:57 e a próxima hora de início da reunião for 14:00, as 14:00 serão exibidas como a única opção de hora de término e você poderá reservar o espaço por três minutos.

3. Toque no intervalo de tempo de término desejado e toque em **Reserva**.

    Uma janela de confirmação aparece com um emoji polegar para cima, hora de início e término da reunião e nome do espaço de reunião.
    :::image type="content" source="../media/panels-reserve-confirmation.png" alt-text="Mensagem de confirmação de reunião ad hoc.":::
O azulejo direito na tela inicial agora aparece em roxo e exibe o texto **Reservado** e o logotipo Teams. Isso indica que o espaço de reunião agora está reservado para uma reunião Teams ad hoc.
  
    :::image type="content" source="../media/panels-right-tile-reserved-adhoc.png" alt-text="Tela inicial mostrando que o espaço de reunião está reservado para uma reunião ad hoc.":::

    > [!NOTE]
    > Se o espaço de reunião for uma sala Microsoft Teams, você poderá participar  dessa reunião Teams com a sala de Microsoft Teams sala ou Surface Hub dispositivos.

### <a name="report-a-problem"></a>Relatar um problema

Para relatar um problema com o dispositivo ou o espaço de reunião, para solicitar uma atualização de recurso ou para fornecer comentários, use o  ícone Configuração na tela inicial.

1. Toque no **Configurações** de engrenagem na tela Inicial.

2. Toque na **opção Relatar um problema** .

    A **tela Enviar Comentários** é exibida em um formato de formulário.
3. Na lista **suspenso Tipo** , selecione o tipo de solicitação.
4. Na lista **suspenso Problema** , selecione a categoria.
5. No campo **texto Título** , digite o título usando o teclado de painéis.
6. No campo de texto abaixo **Título**, digite detalhes adicionais, se necessário.

    > [!NOTE]
    > Não inclua informações de identificação pessoal.

7. Revise suas entradas e toque em **Enviar**.

### <a name="view-or-update-a-device-setting"></a>Exibir ou atualizar uma configuração de dispositivo

Há várias configurações de dispositivo, como cerca, acessibilidade, reinicialização e política de privacidade que você pode exibir ou atualizar diretamente dos painéis. As configurações de dispositivo disponíveis podem diferir com base no OEM (Fabricante de Equipamento Original) do dispositivo. Para obter informações sobre configurações específicas do seu dispositivo, consulte a documentação do OEM.

Para exibir ou atualizar uma configuração de dispositivo:

1. Toque no **Configurações** na tela Inicial.
2. Na tela **Configurações**, toque em **Configurações do dispositivo**.
3. Na tela **Dispositivo Configurações**, toque na configuração que você deseja exibir ou atualizar.
4. Siga o prompt na tela para exibir ou atualizar a configuração.

## <a name="teams-panels-admin-experience"></a>Teams de administrador de painéis

Se você for o administrador da painel do Teams de recursos da [painel do Teams, então](teams-panels.md\#resource-account-provisioning) também será o administrador do **Aplicativo painéis** no dispositivo. Como administrador **do Aplicativo de** Painéis, você pode fazer todas as funções mencionadas na seção experiência [](#teams-panels-end-user-experience) do usuário final, além de gerenciar as configurações do  Aplicativo painéis no dispositivo.

Seus dispositivos de painéis fornecem dois tipos de configurações de administrador. Você deve ser um administrador de dispositivo para acessar as configurações de administrador disponíveis. Os usuários finais não podem acessar essas configurações.

- Configurações de administrador específicas do dispositivo, como exibição, hora e data, idioma, bluetooth, WiFi e assim por diante. Consulte a documentação do OEM para saber mais sobre essas configurações.
- Configurações de administrador **específicas do Aplicativo painéis** em seu dispositivo, como papel de parede e cor do indicador LED. Somente um administrador do **Aplicativo Painéis** pode acessar essas configurações. Como **as configurações** do aplicativo Painéis estão disponíveis como parte das configurações de administrador, você deve ter credenciais de entrada do administrador para o dispositivo  e o Aplicativo painéis  para acessar as configurações do aplicativo Painéis.

> [!NOTE]
> Todas as atualizações para as **configurações do Aplicativo de** Painéis feitas por meio do dispositivo são aplicáveis apenas a esse dispositivo específico. Essas atualizações não afetarão outros dispositivos de painéis em sua organização. Por exemplo, se você alterar a imagem de papel de parede da  tela inicial das configurações do Aplicativo painéis, a imagem de papel de parede mudará somente para esse dispositivo específico.

### <a name="access-panels-app-settings"></a>Configurações do Aplicativo de Painéis de Acesso

Você pode acessar **painéis Configurações** específicas do aplicativo usando a opção **Painels App Configurações** sob as configurações de administrador. As etapas para acessar **o Aplicativo painéis Configurações** podem ser diferentes com base no OEM do seu dispositivo.

Para acessar a **opção Painels app Configurações**:

1. Toque no **Configurações** na tela Inicial.
2. Na tela **Configurações**, toque em **Configurações do dispositivo**.
3. Toque no **administrador Configurações**.

    > [!NOTE]
    > Dependendo do OEM do seu dispositivo, talvez seja necessário inserir a senha do administrador do dispositivo agora ou após a próxima etapa.

4. Role para baixo para encontrar a **opção Painels App Configurações**. Toque nele.
5. Toque no **botão Painels app Configurações** na tela direita.
    A tela com as **configurações do aplicativo Painéis** disponíveis é exibida.

    :::image type="content" source="../media/panels-app-settings-screen.png" alt-text="Esta captura de tela exibe a tela com as configurações do aplicativo Painéis disponíveis.":::

    Use esta tela para atualizar as seguintes **configurações do Aplicativo painéis** para seu dispositivo:

    - [Papel de parede](#update-the-wallpaper)
    - [Indicador LED](#change-the-busy-state-led-color)

#### <a name="pair-a-teams-panel-with-a-microsoft-teams-room-on-android"></a>Emparelhar um painel do Teams com uma sala Microsoft Teams no Android

Para emparelhar um painel do Teams e Teams no Android, ambos os dispositivos devem estar conectados à mesma conta de recurso.

No painel do Teams, entre usando suas credenciais de administrador.

1. Vá para **o Configurações > de Configurações > de Configurações > De Configurações > reuniões > emparelhamento de dispositivos.**

2. Um código de seis dígitos aparecerá na tela Salas do Teams tela frontal do Android. Insira o código no painel Teams.  

#### <a name="meeting-check-in-and-room-release"></a>Check-in de reunião e versão de sala

As configurações de check-in e versão de sala permitem que os usuários entre em uma reunião Teams painéis na sala reservada no início da reunião. Se um usuário não faz check-in dentro de um período de tempo definido após o horário de início da reunião, a sala é liberada e fica disponível para outras pessoas reservarem.

Quando Teams painéis é emparelhado com uma sala Microsoft Teams no Android, as notificações de check-in podem ser habilitadas para aparecer na exibição frontal da sala quando as reuniões são atrasadas.

Para habilitar o check-in e a versão de sala, consulte [Check-in e room release on Microsoft Teams Panels](check-in-and-room-release.md).

#### <a name="room-capacity-warning"></a>Aviso de capacidade de sala

Teams painéis que são emparelhados com uma sala Teams no Android podem exibir uma mensagem de aviso quando uma sala de reunião está com ou mais capacidade. Para usar esse recurso, a sala Teams deve ter uma câmera que suporte a contagem de pessoas. Salas do Teams avisos de capacidade de sala de suporte para Android sem painel do Teams.

Os avisos de capacidade de sala são desligados por padrão. Para ativar a configuração do painel do Teams, primeiro emparelhe um painel do Teams [com uma sala Microsoft Teams no Android](#pair-a-teams-panel-with-a-microsoft-teams-room-on-android). O painel e a Teams Room devem ser assinados na mesma conta de recurso.

 Em seguida, vá para **Configurações > Configurações do dispositivo > Configurações de administrador > configurações do aplicativo Painel**. Em Reuniões **, ative** a **notificação de ocupação da sala Máx**.

#### <a name="view-room-equipment"></a>Exibir equipamento de sala

Quando esse recurso é ligado, os usuários finais podem exibir quais equipamentos estão disponíveis em um espaço em um painel do Teams.

Esse recurso está desligado por padrão e pode ser habilitado por dispositivo. Para a ativar, use [Set-Place](/powershell/module/exchange/set-place?view=exchange-ps) no PowerShell para configurar `AudioDeviceName`os nomes de exibição para , `DisplayDeviceName`, `VideoDeviceName`, `Tags`e `IsWheelChairAccessible`.

Ou você pode habilitar esse recurso no Exchange de administração. Confira [Editar um recurso para](/exchange/recipients-in-exchange-online/manage-resource-mailboxes#edit-a-resource) obter mais informações.



#### <a name="update-the-wallpaper"></a>Atualizar o papel de parede

Alterar a imagem de papel de parede da tela inicial.

1. [Acesso **Painéis Aplicativo Configurações**](#access-panels-app-settings).
2. Toque **em Papel de Parede**.
3. Em **Escolher sua imagem**, selecione uma imagem para definir como a imagem de plano de fundo da tela inicial. Visualize a imagem selecionada em **Plano de Fundo**.
:::image type="content" source="../media/panels-wallpapers-setting.png" alt-text="Esta captura de tela exibe a tela de configurações do papel de parede.":::
4. Voltar na tela inicial e verifique se o papel de parede está atualizado.

#### <a name="change-the-busy-state-led-color"></a>Alterar a cor do LED de estado ocupado

Os administradores podem escolher vermelho ou roxo como a cor LED para indicar que o espaço de reunião está ocupado ou reservado. A cor do LED para indicar um espaço disponível é sempre verde e não pode ser alterada.

1. [Acesso **Painéis Aplicativo Configurações**](#access-panels-app-settings).
2. Toque **em LED Configurações**.
3. Em **Escolher a cor do LED**, selecione a cor desejada.
:::image type="content" source="../media/panels-led-settings.png" alt-text="Esta captura de tela exibe as configurações de estado de ocupado da cor do LED.":::
4. Voltar para a tela inicial e verifique se a cor do LED para o estado de ocupado está atualizada. Se o espaço de reunião estiver disponível no momento, tente agendar uma reunião de teste para verificar a alteração na cor do LED para o estado de disponibilidade.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

Encontre respostas para perguntas frequentes sobre os dispositivos Teams painéis.

**Até que ponto, no futuro, posso ver os detalhes de agendamento de um espaço de reunião?**  
No próximo bloqueio **Calendário** (inferior direito) na tela Inicial, você pode ver os detalhes de agendamento de um espaço de reunião por até 24 horas no futuro a partir da hora atual.

**Posso reservar um espaço de reunião para um tempo futuro do dispositivo Teams painéis?**  
Não, você não pode reservar um espaço de reunião para uma hora futura de painéis. A hora de início é sempre a hora atual de uma reunião ad hoc agendada de painéis.

**Por quanto tempo posso reservar um espaço de reunião disponível para uma reunião ad hoc?**  
Você pode reservar um espaço de reunião disponível a partir do horário atual até o próximo horário de reunião agendado ou até um máximo de 24 horas da hora atual, o que for anterior. Por exemplo, se a hora atual for 10h e a próxima hora de início da reunião for 14:00, você poderá reservar o espaço de reunião das 10:00 às 14:00.
