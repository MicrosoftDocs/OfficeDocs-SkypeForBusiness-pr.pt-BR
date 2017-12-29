---
title: Interoperabilidade entre o Microsoft Teams e o Skype for Business
author: arachmanGitHub
ms.author: MyAdvisor
manager: lolaj
ms.date: 12/12/2017
ms.topic: article
ms.service: msteams
description: "Entenda a interoperabilidade entre o Microsoft Teams e o Skype for Business e como ela afeta as experiências de chat e de chamadas."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: a6593d6e2bc7302817a87c418da4bacb70f03b42
ms.sourcegitcommit: 334fee0485e16a6485055eff586203cc30e6fdc9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2017
---
<a name="microsoft-teams-and-skype-for-business-interoperability"></a>Interoperabilidade entre o Microsoft Teams e o Skype for Business
=======================================================

Se a sua organização já usa o Skype for Business e você pretende começar a usar o Microsoft Teams, é importante saber como configurar a interoperabilidade entre os dois aplicativos.

> [!IMPORTANT]
> Este documento é fornecido para a avaliação inicial do suporte de Planos de Chamadas para o Microsoft Teams. É esperado que os detalhes da política de interoperabilidade do Microsoft Teams sejam alterados no futuro.

A interoperabilidade permite que os usuários do Skype for Business e do Microsoft Teams batam papo e façam chamadas entre si, garantindo a fluidez das comunicações em toda a organização. Para ajudar os profissionais de TI a administrar a adoção do Microsoft Teams, incluímos uma nova política de interoperabilidade do Microsoft Teams, gerenciada por meio de uma sessão do Windows PowerShell remoto do Skype for Business usando cmdlets [`*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype). Use essa política para configurar o Microsoft Teams de acordo com o funcionamento mais adequado para a sua organização.


> [!TIP]
> Para encontrar os cmdlets do PowerShell necessários para a interoperabilidade, digite "CsTeamsInteropPolicy" na caixa **Filtrar** na [documentação de cmdlets do PowerShell para o Skype for Business](https://docs.microsoft.com/powershell/module/skype).

A política de interoperabilidade do Microsoft Teams permite que os profissionais de TI designem o aplicativo preferencial do usuário para receber chats e chamadas. Ela pode ser configurada para manter a comunicação no Microsoft Teams e no Skype for Business em silos ou para permitir que os usuários se comuniquem além dos limites do aplicativo.

A política de interoperabilidade do Microsoft Teams pode ser definida em nível de locatário ou de usuário, além de ser configurada até para permitir que os usuários escolham o aplicativo que desejam usar para receber chats e chamadas.

Essa flexibilidade interna tem como objetivo ajudar a organização a testar, avaliar e migrar para o Microsoft Teams no ritmo e da maneira mais adequada.

> [!NOTE]
> A interoperabilidade entre o Microsoft Teams e o Skype for Business tem suporte entre usuários que são puramente online (Skype for Business Online e Microsoft Teams) e usuários hospedados em implementações locais do Skype for Business em uma topologia de implantação mista (híbrida).

## <a name="what-interoperability-means"></a>O que quer dizer interoperabilidade
Interoperabilidade é a capacidade que os usuários do Microsoft Teams e do Skype for Business têm de bater papo (IM) e fazer ligações entre si no Microsoft Teams e no Skype for Business.

Conforme as organizações iniciam a jornada de migração do Skype for Business para o Microsoft Teams, a expectativa é de que haja uma combinação de usuários com clientes diferentes na organização.

Para garantir a continuidade da produtividade, o Microsoft Teams permite que os usuários se comuniquem entre si independentemente do aplicativo que usam (Microsoft Teams ou Skype for Business).

As experiências de interoperabilidade com suporte incluem:
- Os usuários do Skype for Business que não usam o Microsoft Teams podem bater papo com os usuários do Microsoft Teams e vice-versa<p>
![Experiência de interoperabilidade de chat no Microsoft Teams](media/Interop_chat_experience_from_Teams.png)<br>
- Os usuários do Skype for Business podem fazer chamadas para usuários do Microsoft Teams com voz e vídeo e vice-versa. As opções avançadas de chamadas, como a transferência e o encaminhamento de chamadas, continuarão funcionando, mesmo para chamadas de interoperabilidade.<p>
![Experiência de interoperabilidade de chamadas no Microsoft Teams](media/Interop_calling_experience_from_Teams.png)<br>

> [!NOTE]
> Do ponto de vista de um usuário do Skype for Business, os chats e as chamadas com o Microsoft Teams aparecerão como chats e chamadas básicas do Skype for Business. Examine os detalhes na seção [Limitações das experiências de interoperabilidade](#interop-experiences-limitations).

> [!IMPORTANT]
> No momento, não há suporte para a presença unificada entre o Microsoft Teams e o Skype for Business. Isso quer dizer que o Microsoft Teams e o Skype for Business exibirão seus estados de presença independentes. Para saber quando o suporte à presença unificada estará disponível, veja o [Skype for Business to Microsoft Teams Capabilities Roadmap](https://aka.ms/skype2teamsroadmap).

## <a name="interop-requirements"></a>Requisitos de interoperabilidade
Para habilitar as funcionalidades de interoperabilidade, os usuários devem atender aos seguintes critérios:
- Os usuários devem ter o Microsoft Teams habilitado (e/ou licenciado)
- Os usuários devem ter o Skype for Business Online habilitado (e/ou licenciado)
    - Isso se aplica a usuários que planejam usar somente o Microsoft Teams ou usá-lo como seu aplicativo principal de chat e chamadas
- Em uma implantação híbrida do Skype for Business,
    - Os usuários hospedados no Skype for Business local (ou em qualquer versão do Lync Server com suporte para implantações híbridas do Skype for Business) têm interoperabilidade com usuários da nuvem que usam o Microsoft Teams
    - Os usuários da nuvem que planejam usar o Microsoft Teams como aplicativo principal de chat e chamadas devem ter o Skype for Business Online habilitado (e/ou licenciado)

## <a name="supported-topologies-for-interop"></a>Topologias com suporte para interoperabilidade
A interoperabilidade entre o Microsoft Teams e o Skype for Business tem suporte primário para as seguintes topologias de implantação do Skype for Business:
- Apenas Skype for Business Online
- Skype for Business híbrido (implantação mista do Skype for Business Online e do Skype for Business local)

### <a name="skype-for-business-online-only-topology"></a>Topologia apenas com o Skype for Business Online
As organizações apenas com implantações do Skype for Business Online podem aproveitar a interoperabilidade de chat e chamadas entre usuários do Skype for Business Online e usuários do Microsoft Teams.

Nessa topologia, os usuários que têm o Microsoft Teams configurado como aplicativo principal de chat e chamadas também devem ter o Skype for Business Online habilitado para que a interoperabilidade funcione.

![Interoperabilidade em uma topologia de implantação apenas com o Skype for Business Online](media/Interop_SkypeforBusinessOnlineOnly_topology.png)

### <a name="skype-for-business-hybrid-deployment-topology"></a>Topologia de implantação híbrida do Skype for Business
As organizações com uma implantação que consiste na implantação mista do Skype for Business Online e do Skype for Business Server (local) em uma topologia de implantação híbrida podem aproveitar a interoperabilidade de chat e chamadas entre usuários do Skype for Business (hospedados online ou localmente) e usuários do Microsoft Teams.

Da mesma forma que na topologia de implantação apenas com o Skype for Business Online, os usuários que têm o Microsoft Teams configurado como aplicativo principal de chat e chamadas também devem ter o Skype for Business Online habilitado e devem estar hospedados nele para que a interoperabilidade funcione.

![Interoperabilidade em uma topologia de implantação híbrida do Skype for Business](media/Interop_SkypeforBusinessHybrid_topology.png)

> [!IMPORTANT]
> O suporte à interoperabilidade de implantações híbridas do Skype for Business não incluem as funcionalidades do Hybrid Voice fornecidas pela CCE (Cloud Connector Edition) ou a conectividade PSTN local usando a implantação existente, comumente chamada de OPCH (On Prem Config Hybrid). Os usuários do Microsoft Teams não podem ter as funcionalidades de chamadas PSTN habilitadas usando a CCE ou a OPCH.

### <a name="interop-experiences-limitations"></a>Limitações das experiências de interoperabilidade
No momento, além da falta da presença unificada entre o Microsoft Teams e o Skype for Business, o que faz cada um dos aplicativos ter seu próprio estado de presença independente, há recursos que não estão disponíveis para a interoperabilidade de experiências de chat e chamadas entre o Microsoft Teams e o Skype for Business.

Para a interoperabilidade de chat, estas são as limitações:
- As conversas (chats) com vários participantes (em grupo) no Microsoft Teams podem incluir apenas participantes que usam o Microsoft Teams
- As conversas por mensagens instantâneas (chats) com vários participantes no Skype for Business podem incluir apenas participantes que usam o Skype for Business
- Não há suporte para a transferência de arquivos em conversas de chat com dois participantes ou de anexos de arquivos em conversas com vários participantes entre o Microsoft Teams e o Skype for Business e vice-versa
- A interoperabilidade de chat não persiste no Microsoft Teams
- Não há suporte para markdown, rich text, conjunto completo de emoticons etc. no Microsoft Teams para a interoperabilidade de chats

Para a interoperabilidade de chamadas, estas são as limitações:
- Não há suporte para o compartilhamento de tela (compartilhamento da área de trabalho ou do aplicativo) entre o Microsoft Teams e o Skype for Business
- Não há suporte para o escalonamento de chamadas de voz e vídeo ponto a ponto (P2P) existentes para chamadas com vários participantes que envolvem usuários do Microsoft Teams e do Skype for Business

## <a name="managing-interoperability"></a>Gerenciamento da interoperabilidade
Para gerenciar a interoperabilidade entre o Microsoft Teams e o Skype for Business, é possível utilizar uma nova política chamada política de interoperabilidade do Microsoft Teams para controlar para onde enviar os chats e encaminhar as chamadas, o Microsoft Teams ou o Skype for Business. Essa política pode ser configurada para todos os usuários da organização (política global) ou aplicada individualmente, sendo gerenciada na sessão do Windows PowerShell remoto do Skype for Business usando cmdlets [`*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps).

Por padrão, essa política é configurada para garantir que o Microsoft Teams e o Skype for Business possam ser usados lado a lado com interoperabilidade mínima entre eles. Essa abordagem tem como objetivo garantir que os processos de negócios e as comunicações atuais em sua organização não sejam interrompidas por causa da adoção do Microsoft Teams.

### <a name="interop-policy-overview"></a>Visão geral da política de interoperabilidade
A política de interoperabilidade do Microsoft Teams consiste nos seguintes parâmetros:

|Parâmetro                    |Valores possíveis      |Descrição  |
|-----------------------------|---------------------|---------|
|`ChatDefaultClient`          | Default, SfB, Teams | Este parâmetro especifica o aplicativo de chat padrão        |
|`CallingDefaultClient`       | Default, SfB, Teams | Este parâmetro especifica o aplicativo de chamadas padrão        |
|`AllowEndUserClientOverride` | True, False         | Este parâmetro especifica se os usuários podem substituir o aplicativo de chat e de chamadas padrão         |

> [!WARNING]
> Embora no momento seja possível criar uma política de interoperabilidade do Microsoft Teams com valores independentes para os parâmetros `ChatDefaultClient` e `CallingDefaultClient`, esperamos que isso mude no futuro. Por enquanto, verifique se você está usando o mesmo valor para os dois parâmetros.

#### <a name="chat-default-client"></a>Cliente de chat padrão
O parâmetro `ChatDefaultClient` define como os chats são encaminhados entre o Microsoft Teams e o Skype for Business, e o valor global padrão desse parâmetro é definido como **Default**.

> [!IMPORTANT]
> No momento, o parâmetro `ChatDefaultClient` não é considerado pelo Microsoft Teams. A documentação será atualizada para descrever o comportamento esperado assim que o parâmetro for considerado pelo Microsoft Teams. As funcionalidades de interoperabilidade de chat entre o Microsoft Teams e o Skype for Business controladas em nível de locatário continuarão funcionando da mesma forma.

#### <a name="calling-default-client"></a>Cliente de chamadas padrão
O parâmetro `CallingDefaultClient` define como as chamadas são encaminhadas entre o Microsoft Teams e o Skype for Business, e o valor global padrão desse parâmetro é definido como **Default**.

Veja a seguir a explicação detalhada de como cada configuração desse parâmetro afeta o comportamento dos clientes do Microsoft Teams e do Skype for Business.

|Chamada feita no  |Configuração: padrão; chamada recebida no  |Configuração: Microsoft Teams; chamada recebida no  |Configuração: SfB; chamada recebida no  |
|---------|---------|---------|---------|
|**Skype for Business**     |Skype for Business         |Microsoft Teams        |Skype for Business         |
|**Microsoft Teams**     |Microsoft Teams         |Microsoft Teams         |Skype for Business         |
|**PSTN**   |Skype for Business        |Microsoft Teams        |Skype for Business         |
|**Skype for Business federado**     |Skype for Business         |Skype for Business         |Skype for Business         |

> [!IMPORTANT]
> No momento, a alteração de `CallingDefaultClient` para o Microsoft Teams também afeta as chamadas para telefones IP do Skype for Business. As chamadas de entrada não serão recebidas em telefones e vão tocar somente nos clientes do Microsoft Teams. Consulte o [Skype for Business to Microsoft Teams Capabilities Roadmap](https://aka.ms/skype2teamsroadmap) para obter informações sobre o suporte para telefones SIP certificados existentes.

#### <a name="allowing-user-choice"></a>Permissão para que o usuário escolha
O parâmetro `AllowEndUserClientOverride` aceita valores boolianos (**TRUE** ou **FALSE**) e, quando definido como **TRUE**, o Microsoft Teams permite que os usuários selecionem onde desejam receber chamadas, no Microsoft Teams ou no Skype for Business. Os usuários também podem alterar seu aplicativo principal a qualquer momento.

![Opção preferencial de aplicativo de chamadas](media/Preferred_calling_application_option.png)

O valor padrão global desse parâmetro é **FALSE**. Com ele, os usuários não poderão escolher o aplicativo principal sem a intervenção do administrador.

## <a name="teams-interop-policy-special-cases"></a>Casos especiais da política de interoperabilidade do Microsoft Teams
Ao atribuir a política de interoperabilidade do Microsoft Teams, os usuários que continuam hospedados no Skype for Business local, em uma topologia de implantação mista (híbrida), os usuários com Hybrid Voice (por meio da CCE ou OPCH) e os usuários com fluxos de trabalho especializados do Skype for Business são considerados casos especiais e exigem atenção especial sobre a política atribuída a eles.

### <a name="policy-for-skype-for-business-on-premises-users"></a>Política para usuários do Skype for Business local
Em uma topologia de implantação mista (híbrida), os usuários hospedados no Skype for Business local nunca devem ter os parâmetros `ChatDefaultClient` e `CallingDefaultClient` da política definidos como Microsoft Teams. Se isso ocorrer, eles não conseguirão receber chats e chamadas. Use a seguinte definição da política para usuários locais:

|Parâmetro  |Valor  |
|---------|---------|
|`ChatDefaultClient`    |Default ou SfB         |
|`CallingDefaultClient`     |Default ou SfB         |
|`AllowEndUserClientOverride`     |False         |

> [!IMPORTANT]
> Ao migrar usuários do Skype for Business Online para o Skype for Business local ou vice-versa, é preciso garantir que a política de interoperabilidade do Microsoft Teams atribuída ao usuário esteja de acordo com o comportamento que deve ser imposto. Lembre-se de que não é possível configurar os usuários locais para usar o Microsoft Teams como aplicativo principal de chat e chamadas.

### <a name="policy-for-hybrid-voice-users-cce-or-opch"></a>Política para usuários do Hybrid Voice (CCE ou OPCH)
Os usuários do Skype for Business Online que têm o Sistema de Telefonia habilitado com Hybrid Voice (por meio da CCE ou OPCH) não podem receber chamadas PSTN no Microsoft Teams. Ao atribuir a política de interoperabilidade do Microsoft Teams para usuários do Hybrid Voice, use a seguinte definição da política:

|Parâmetro  |Valor  |
|---------|---------|
|`ChatDefaultClient`    |Default ou SfB ou Teams         |
|`CallingDefaultClient`     |Default ou SfB         |
|`AllowEndUserClientOverride`     |False         |

### <a name="policy-for-users-with-specialized-skype-for-business-workflows"></a>Política para usuários com fluxos de trabalho especializados do Skype for Business
Em alguns casos, um grupo de usuários pode usar aplicativos de terceiros que dependem do Skype for Business (por exemplo, call centers, recepcionistas etc.). Nesses casos, você deve garantir que eles permaneçam no Skype for Business até que tenham funcionalidades equivalentes no Microsoft Teams. Para esses usuários, utilize a seguinte definição da política:

|Parâmetro  |Valor  |
|---------|---------|
|`ChatDefaultClient`    |Default ou SfB         |
|`CallingDefaultClient`     |Default ou SfB         |
|`AllowEndUserClientOverride`     |False         |