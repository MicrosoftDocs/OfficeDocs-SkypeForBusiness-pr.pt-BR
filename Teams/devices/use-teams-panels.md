---
title: Como usar dispositivos de painéis do Microsoft Teams
ms.author: v-mdhiman
author: ManikaDhiman
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
localization_priority: Normal
description: Este artigo fornece orientações sobre como usar dispositivos de painéis do Teams.
ms.openlocfilehash: f5afdb5ec9ec7cb6d6c7e86487dbaf27af98bafc
ms.sourcegitcommit: 2eaf80bca6dfad367283e57662d81a809c9437e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/22/2021
ms.locfileid: "50997439"
---
# <a name="how-to-use-microsoft-teams-panels"></a>Como usar painéis do Microsoft Teams

Os painéis do Microsoft Teams são dispositivos de exibição digital compactos que são montados fora dos espaços de reunião, normalmente ao lado de entradas. Esses painéis touchscreen são dispositivos dedicados do Microsoft Teams que fornecem uma visão geral sobre seu espaço de reunião e a reunião agendada. Com os indicadores de LED e tela inicial codificados por cores vibrantes, você pode determinar se o espaço está disponível ou reservado de uma distância. Você pode usar painéis do Teams para reservar um espaço de reunião disponível para uma reunião ad hoc, no local.

Os dispositivos de painéis do Teams vêm pré-instalados com o Microsoft Teams e exibem detalhes da reunião agendados por meio de calendários do Outlook ou do Teams.

Este artigo fornece orientações, para usuários finais e administradores, sobre como usar os dispositivos de painéis do Teams. Ele também fornece respostas às [perguntas frequentes sobre](#frequently-asked-questions) como usar esses dispositivos.

Para obter uma visão geral dos dispositivos de painéis e as diretrizes sobre como planejar, entregar e gerenciá-los em sua organização, consulte [Deploy Microsoft Teams panels](teams-panels.md).

Para começar rapidamente, confira [Começar a trabalhar com painéis do Teams.](https://support.microsoft.com/office/get-started-with-teams-panels-fa5e85d1-7ff3-4f11-b0b0-277e2302c8be)

## <a name="teams-panels-end-user-experience"></a>Painéis do Teams experiência do usuário final

Explore a [tela inicial do](#explore-teams-panels-home-screen) dispositivo de painéis do Teams para exibir o espaço de reunião e os detalhes da reunião. Ou toque e role no painel touchscreen para fazer outras ações.

Use seus dispositivos de painéis do Teams para:

- [Exibir detalhes do espaço de reunião e disponibilidade, detalhes da reunião, reservas futuras](#explore-teams-panels-home-screen)
- [Reservar um espaço de reunião disponível](#reserve-meeting-spaces-for-ad-hoc-meetings)
- [Relatar um problema](#report-a-problem)
- [Exibir ou atualizar uma configuração de dispositivo](#view-or-update-a-device-setting)

## <a name="explore-teams-panels-home-screen"></a>Explorar tela inicial dos painéis do Teams

A tela inicial é a interface visual principal do dispositivo de painéis do Teams.  

Na tela Inicial, você pode exibir detalhes de local e reunião, reservar um espaço, exibir reservas futuras e identificar o status de disponibilidade atual.

A captura de tela a seguir mostra partes ou blocos diferentes na tela Inicial dos painéis do Teams:

:::image type="content" source="../media/panels-home-screen-explanation.png" alt-text="Esta captura de tela exibe diferentes áreas na tela Inicial dos painéis do Teams":::

Consulte a tabela a seguir para uma descrição de cada telha:

Tile | Descrição
:---|:---
**1-Detalhes do espaço de reunião, dia, data e hora atuais** | Exibe a hora atual, o dia, a data e o nome do espaço de reunião. O nome do espaço de reunião é o nome da conta de recurso que se inscreveu nos painéis.
**2-Disponibilidade de espaço de reunião e detalhes da reunião** | Indica a disponibilidade do espaço de reunião e exibe os detalhes da reunião. Consulte [Disponibilidade de espaço de reunião e o tile de detalhes da reunião.](#meeting-space-availability-and-meeting-details-tile)
**Calendário 3-Futuro** | Exibe o calendário e a disponibilidade do espaço de reunião por até 24 horas a partir da hora atual. Role para cima ou para baixo para determinar quais intervalos de tempo estão disponíveis e quais são reservados.
**4-Settings** | Exibe o **ícone Configurações.** Toque nele para relatar um problema ou atualizar as configurações de dispositivo disponíveis.

### <a name="meeting-space-availability-and-meeting-details-tile"></a>Espaço de reunião e o tile de detalhes da reunião

A aparência desse telha e seus recursos variam dependendo da disponibilidade do espaço de reunião e do tipo de reserva.

#### <a name="meeting-space-is-reserved-for-a-scheduled-meeting"></a>O espaço de reunião é reservado para uma reunião agendada

O azulejo aparece em roxo para um espaço de reunião reservado para uma reunião agendada (agendada por meio do Outlook ou do Teams). Ele exibe o título da reunião em texto proeminente, horários de início e término da reunião e o nome do organizador da reunião. Para uma reunião do Teams, o logotipo do Teams também aparece. Com os detalhes da reunião exibidos com destaque, os participantes podem confirmar facilmente que estão no espaço de reunião certo, no momento certo e na reunião certa.

:::image type="content" source="../media/panels-right-tile-scheduled-meeting.png" alt-text="Painéis do Teams Tela inicial mostrando que o espaço de reunião está reservado para uma reunião agendada":::

> [!NOTE]
>
> - Depois de agendar uma reunião, pode levar até 90 segundos para que o calendário sincronize e reflita na tela de painéis.
> - Para uma [reunião agendada marcada como privada,](https://support.microsoft.com/office/make-an-appointment-or-meeting-private-dc3898f0-22f5-45c6-8cc8-b4d4db84111d) **a** reunião privada é exibida em vez do título real da reunião.

#### <a name="meeting-space-is-reserved-for-an-ad-hoc-meeting"></a>O espaço de reunião é reservado para uma reunião ad hoc

O azulejo aparece em roxo para um espaço de reunião reservado [para uma reunião ad hoc.](#reserve-meeting-spaces-for-ad-hoc-meetings) Ele exibe **Reservado em texto** proeminente juntamente com os horários de início e término da reunião. As reuniões ad hoc são agendadas automaticamente como reuniões do Teams, portanto, o logotipo do Teams sempre aparece na tela.

:::image type="content" source="../media/panels-right-tile-reserved-adhoc.png" alt-text="Painéis do Teams Tela inicial mostrando que o espaço de reunião está reservado para uma reunião ad hoc":::

#### <a name="meeting-space-is-available"></a>O espaço de reunião está disponível

O azulejo aparece em verde para um espaço de reunião disponível. Ele exibe **Available em texto** proeminente, e um botão **Reserva** também aparece que você pode tocar para reservar o espaço de reunião para uma reunião [ad hoc](#reserve-meeting-spaces-for-ad-hoc-meetings). Você pode verificar o próximo calendário do espaço de reunião (azulejo inferior direito) para decidir a hora de término da reunião ad hoc.

:::image type="content" source="../media/panels-right-tile-available-status.png" alt-text="Esta captura de tela mostra como a tela Inicial dos painéis do Teams aparece quando o espaço de reunião está disponível":::

## <a name="reserve-meeting-spaces-for-ad-hoc-meetings"></a>Reservar espaços de reunião para reuniões ad hoc

Você pode reservar [um espaço de reunião disponível](#meeting-space-is-available) diretamente de painéis para uma reunião ad hoc. Todas as reuniões ad hoc são agendadas automaticamente como reuniões do Teams. No entanto, uma vez reservado, você não pode liberar ou não reservar esse espaço de reunião por meio de painéis. Somente os administradores da conta de recurso do dispositivo podem cancelar a reunião ad hoc (por meio do calendário do Outlook ou do Teams) para não reservar o espaço.

Para reuniões ad hoc reservadas diretamente de painéis:

- A hora de início é sempre a hora atual e, como tal, você não pode agende-la para uma hora futura.
- A hora de término pode ser até a próxima reunião agendada ou até 24 horas a partir da hora atual, o que for anterior. Verifique o **bloqueio Calendário Futuro** na tela Inicial para determinar os intervalos de tempo durante os quais o espaço de reunião está disponível ou reservado.

Para reservar um espaço de reunião disponível para uma reunião ad hoc:

1. Na tela Inicial, toque no **botão Reserva.**
    :::image type="content" source="../media/panels-reserve.png" alt-text="Tela inicial dos painéis do Teams mostrando o botão Reserva":::
2. Na tela **de reunião Ad hoc,** revise as opções de hora de término disponíveis. Você pode usar as setas direita ou esquerda para procurar as opções de hora de término disponíveis.

    :::image type="content" source="../media/panels-reserve-endtime.png" alt-text="Tela de reunião ad hoc mostrando intervalos de tempo de término":::

    > [!Note]
    >
    > - As opções de hora final são exibidas em intervalos de 15 minutos de uma hora.
    > - A hora de término é padrão para o próximo intervalo de 15 minutos que é pelo menos cinco minutos após a hora atual. Por exemplo, se a hora atual for 13:57, a hora de término padrão será exibida como 14:15 e não 14:00. Isso impede que os usuários reservem o espaço por cinco minutos ou menos. Na captura de tela acima, a hora de término padrão é exibida como 14:00 PM, que é o próximo intervalo de 15 minutos que é pelo menos cinco minutos após a hora atual (13:53 PM).
    > - Uma exceção à regra acima é quando a hora de início da próxima reunião está dentro de cinco minutos a partir da hora atual. Nesses casos, você pode reservar o espaço até a próxima hora de início da reunião. Por exemplo, se a hora atual for 13:57 e a próxima hora de início da reunião for 14:00, as 14:00 serão exibidas como a única opção de hora de término e você poderá reservar o espaço por três minutos.

3. Toque no intervalo de tempo de término desejado e toque em **Reserva**.

    Uma janela de confirmação aparece com um emoji polegar para cima, hora de início e término da reunião e nome do espaço de reunião.
    :::image type="content" source="../media/panels-reserve-confirmation.png" alt-text="Mensagem de confirmação de reunião ad hoc":::
O azulejo direito na tela Inicial agora aparece em roxo e exibe o **texto Reservado** e o logotipo do Teams. Isso indica que o espaço de reunião agora está reservado para uma reunião ad hoc do Teams.
  
    :::image type="content" source="../media/panels-right-tile-reserved-adhoc.png" alt-text="Tela inicial mostrando que o espaço de reunião está reservado para uma reunião ad hoc":::

    > [!NOTE]
    > Se o espaço de reunião for  uma Sala do Microsoft Teams, você poderá participar dessa reunião do Teams com a Sala do Microsoft Teams na sala ou dispositivos Surface Hub.

### <a name="report-a-problem"></a>Relatar um problema

Para relatar um problema com o dispositivo ou o espaço de reunião, para  solicitar uma atualização de recurso ou para fornecer comentários, use o ícone Configuração na tela inicial.

1. Toque no **ícone de engrenagem Configurações** na tela inicial.

2. Toque na **opção Relatar um problema.**

    A **tela Enviar Comentários** é exibida em um formato de formulário.
3. Na lista **suspenso Tipo,** selecione o tipo de solicitação.
4. Na lista **suspenso Problema,** selecione a categoria.
5. No campo **texto Título,** digite o título usando o teclado de painéis.
6. No campo de texto abaixo **Título**, digite detalhes adicionais, se necessário.

    > [!NOTE]
    > Não inclua informações de identificação pessoal.

7. Revise suas entradas e toque em **Enviar**.

### <a name="view-or-update-a-device-setting"></a>Exibir ou atualizar uma configuração de dispositivo

Há várias configurações de dispositivo, como cerca, acessibilidade, reinicialização e política de privacidade que você pode exibir ou atualizar diretamente dos painéis. As configurações de dispositivo disponíveis podem diferir com base no OEM (Fabricante de Equipamento Original) do dispositivo. Para obter informações sobre configurações específicas do seu dispositivo, consulte a documentação do OEM.

Para exibir ou atualizar uma configuração de dispositivo:

1. Toque no **ícone Configurações** na tela Inicial.
2. Na tela **Configurações,** toque em **Configurações do dispositivo**.
3. Na tela **Configurações do** Dispositivo, toque na configuração que você deseja exibir ou atualizar.
4. Siga o prompt na tela para exibir ou atualizar a configuração.

## <a name="teams-panels-admin-experience"></a>Experiência de administrador de painéis do Teams

Se você for o administrador da conta de recurso do painel do [Teams,](teams-panels.md\#resource-account-provisioning)você também será o administrador do **Aplicativo de** Painéis no dispositivo. Como administrador do Aplicativo **de** Painéis, você pode fazer [](#teams-panels-end-user-experience) todas as funções mencionadas na  seção experiência do usuário final, além de gerenciar as configurações do Aplicativo painéis no dispositivo.

Seus dispositivos de painéis fornecem dois tipos de configurações de administrador. Você deve ser um administrador de dispositivo para acessar as configurações de administrador disponíveis. Os usuários finais não podem acessar essas configurações.

- Configurações de administrador específicas do dispositivo, como exibição, hora e data, idioma, bluetooth, WiFi e assim por diante. Consulte a documentação do OEM para saber mais sobre essas configurações.
- Configurações de administrador **específicas** do Aplicativo painéis em seu dispositivo, como papel de parede e cor do indicador LED. Somente um administrador do **Aplicativo Painéis** pode acessar essas configurações. Como **as configurações** do aplicativo Painéis estão disponíveis como parte das configurações de  administrador, você  deve ter credenciais de entrada do administrador para o dispositivo e o Aplicativo painéis para acessar as configurações do aplicativo Painéis.

> [!NOTE]
> Todas as atualizações para as **configurações do Aplicativo de** Painéis feitas por meio do dispositivo são aplicáveis apenas a esse dispositivo específico. Essas atualizações não afetarão outros dispositivos de painéis em sua organização. Por exemplo, se você alterar a  imagem de papel de parede da tela inicial das configurações do Aplicativo painéis, a imagem de papel de parede mudará somente para esse dispositivo específico.

### <a name="access-panels-app-settings"></a>Configurações do Aplicativo de Painéis de Acesso

Você pode acessar **Painéis Configurações** específicas do aplicativo usando a opção **Configurações** do Aplicativo painéis nas configurações do administrador. As etapas para acessar **Painéis Configurações do** Aplicativo podem ser diferentes com base no OEM do seu dispositivo.

Para acessar a **opção Configurações do Aplicativo painéis:**

1. Toque no **ícone Configurações** na tela Inicial.
2. Na tela **Configurações,** toque em **Configurações do dispositivo**.
3. Toque nas **Configurações do Administrador**.

    > [!NOTE]
    > Dependendo do OEM do seu dispositivo, talvez seja necessário inserir a senha do administrador do dispositivo agora ou após a próxima etapa.

4. Role para baixo para encontrar a **opção Configurações do Aplicativo de** Painéis. Toque nele.
5. Toque no **botão Configurações do Aplicativo de Painéis** na tela direita.
    A tela com as configurações do aplicativo **Painéis** disponíveis é exibida.

    :::image type="content" source="../media/panels-app-settings-screen.png" alt-text="Esta captura de tela exibe a tela com as configurações do aplicativo Painéis disponíveis":::

    Use esta tela para atualizar as seguintes **configurações do Aplicativo painéis** para seu dispositivo:

    - [Papel de parede](#update-the-wallpaper)
    - [Indicador LED](#change-the-busy-state-led-color)

#### <a name="update-the-wallpaper"></a>Atualizar o papel de parede

Alterar a imagem de papel de parede da tela inicial.

1. [Configurações do aplicativo de **Painéis de Acesso.**](#access-panels-app-settings)
2. Toque **em Papel de Parede**.
3. Em **Escolher sua imagem,** selecione uma imagem para definir como a imagem de plano de fundo da tela inicial. Visualizar a imagem selecionada em **Plano de Fundo**.
:::image type="content" source="../media/panels-wallpapers-setting.png" alt-text="Esta captura de tela exibe a tela de configurações do papel de parede":::
4. Volte para a tela inicial e verifique se o papel de parede foi atualizado.

#### <a name="change-the-busy-state-led-color"></a>Alterar a cor do LED de estado ocupado

Os administradores podem escolher vermelho ou roxo como a cor LED para indicar que o espaço de reunião está ocupado ou reservado. A cor do LED para indicar um espaço disponível é sempre verde e não pode ser alterada.

1. [Configurações do aplicativo de **Painéis de Acesso.**](#access-panels-app-settings)
2. Toque **em Configurações de LED**.
3. Em **Escolher a cor do LED,** selecione a cor desejada.
:::image type="content" source="../media/panels-led-settings.png" alt-text="Esta captura de tela exibe as configurações de estado de ocupado de cor led":::
4. Volte para a tela inicial e verifique se a cor do LED para o estado de ocupado está atualizada. Se o espaço de reunião estiver disponível no momento, tente agendar uma reunião de teste para verificar a alteração na cor do LED para o estado de disponibilidade.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

Encontre respostas para perguntas frequentes sobre os dispositivos de painéis do Teams.

**Até que ponto, no futuro, posso ver os detalhes de agendamento de um espaço de reunião?**  
No próximo bloqueio **Calendário** (inferior direito) na tela Inicial, você pode ver os detalhes de agendamento de um espaço de reunião por até 24 horas no futuro a partir da hora atual.

**Posso reservar um espaço de reunião para uma hora futura do dispositivo de painéis do Teams?**  
Não, você não pode reservar um espaço de reunião para uma hora futura de painéis. A hora de início é sempre a hora atual de uma reunião ad hoc agendada de painéis.

**Por quanto tempo posso reservar um espaço de reunião disponível para uma reunião ad hoc?**  
Você pode reservar um espaço de reunião disponível a partir do horário atual até o próximo horário de reunião agendado ou até um máximo de 24 horas da hora atual, o que for anterior. Por exemplo, se a hora atual for 10h e a próxima hora de início da reunião for 14:00, você poderá reservar o espaço de reunião das 10:00 às 14:00.
