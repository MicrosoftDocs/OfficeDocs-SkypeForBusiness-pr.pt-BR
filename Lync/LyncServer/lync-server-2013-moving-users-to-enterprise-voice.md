---
title: 'Lync Server 2013: movendo usuários para o Enterprise Voice'
description: 'Lync Server 2013: movendo usuários para o Enterprise Voice.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving users to Enterprise Voice
ms:assetid: a2df6d51-5cf2-4d3e-8f97-496af5fd5e5e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412758(v=OCS.15)
ms:contentKeyID: 48184958
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41b075f916f4d81d8d3c24c24c7393be58e10a92
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542007"
---
# <a name="moving-users-to-enterprise-voice-in-lync-server-2013"></a>Movendo usuários para o Enterprise Voice no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-18_

Se você estiver movendo usuários de uma infraestrutura de telefonia PBX existente para o Enterprise Voice, o processo de implantação incluirá algumas etapas que não fazem parte do processo de planejamento já descrito no [Planning for Enterprise Voice no Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md). Para informações sobre a migração de usuários de uma implantação anterior do Enterprise Voice, consulte os documentos de migração incluídos na sua mídia de instalação.

O processo de migração dos usuários de uma infraestrutura de telefonia existente para o Enterprise Voice consiste nas seguintes etapas:

1.  Designar números de telefone principais.

2.  Habilitar usuários para o Enterprise Voice.

3.  Preparar planos de discagem para os usuários.

4.  Planejar as políticas de voz dos usuários.

5.  Planejar rotas de chamadas.

6.  Configurar o PBX ou Tronco SIP para rerotear chamadas para usuários habilitados para o  Enterprise Voice.

7.  Mover usuários para a Unificação de mensagens (UM) do Exchange (recomendado).

Este tópico descreve o planejamento necessário em cada uma dessas etapas.

<div>

## <a name="step-1-designate-primary-phone-numbers"></a>Etapa 1. Designar números de telefone principais

O Enterprise Voice integra voz a outras mídias de mensagens de forma que, quando uma chamada recebida chega ao servidor, o servidor mapeia o número para o URI do SIP do usuário e, em seguida, bifurca a chamada para todos os pontos de extremidade do cliente associados a esse URI do SIP. Esse processo exige que cada usuário esteja associado a um número de telefone principal.

Um número de telefone principal deve ser:

  - Globalmente exclusivo ou, no caso de ramais internos, exclusivo na empresa.

  - Próprio da empresa e roteável. Números pessoais não devem ser usados.

Os usuários da empresa podem ter dois ou mais números de telefone listados para eles nos serviços de domínio do Active Directory. Todos os números de telefone associados a um usuário específico podem ser exibidos ou alterados na respectiva folha de propriedades no snap-in Usuários e Computadores do Active Directory.

A caixa **Número de telefone** na guia **Geral** da caixa de diálogo **Propriedades do Usuário** deve conter o número de trabalho principal do usuário. Normalmente, esse número é designado como o número de telefone principal do usuário.

Alguns usuários podem ter requisitos especiais (como um executivo que deseja que as chamadas recebidas sejam roteadas por um assistente administrativo), mas essas exceções devem ser limitadas somente àquelas nas quais a necessidade seja clara e crítica.

Após a escolha do número principal, ele deverá ser:

  - Normalizado no formato E.164, sempre que possível.

  - Copiado para o atributo **msRTCSIP-line** do Active Directory.
    
    <div>
    

    > [!NOTE]  
    > <STRONG>Coexistência com o RCC (controle de chamada remota).</STRONG><BR>O RCC é a capacidade de usar o Lync Server para monitorar e controlar um telefone de PBX de área de trabalho. O controle é roteado pelo servidor, que atua como um gateway para o PBX. Embora você não possa configurar um usuário para ambos, RCC e Enterprise Voice, a configuração do URI de Linha designa o número de telefone principal do usuário em ambos os casos.<BR>Se você tem uma infraestrutura de PBX existente que deseja que usuários selecionados continuem usando, pode introduzir o Enterprise Voice de forma incremental na sua organização. Para obter detalhes sobre esse cenário de implantação, consulte <A href="lync-server-2013-direct-sip-deployment-options.md">Direct SIP Deployment Options in Lync Server 2013</A> na documentação de planejamento.<BR>Em versões anteriores, você pode habilitar o RCC e o Enterprise Voice para um usuário, mas apenas se você também configurou o usuário para bifurcação dupla, um recurso no qual uma chamada de entrada tocará o telefone PBX do usuário e o Communicator simultaneamente. No Lync Server 2010, não há suporte para a bifurcação dupla.

    
    </div>

Há três métodos para popular o atributo **msRTCSIP-line**:

  - Microsoft Identity Integration Server (recomendado)

  - A página **usuários** no painel de controle do Lync Server

Onde muitos números de telefone devem ser processados, um script personalizado desenvolvido pela sua organização é a melhor opção. Dependendo de como a organização representa os números de telefone nos Serviços de Domínio Active Directory, o script talvez precise normalizar números de telefone principais no formato E.164 antes de copiá-los para o atributo **msRTCSIP-line**.

  - Se a sua organização mantém todos os números de telefone dos Serviços de Domínio Active Directory em um único formato, e se esse formato é o E.164, então o script só precisará gravar cada número de telefone principal no atributo **msRTCSIP-line**.

  - Se a sua organização mantém todos os números de telefone dos Serviços de Domínio Active Directory em um único formato, mas esse formato não é o E.164, o script deverá definir uma regra de normalização apropriada para converter os números de telefone principais do formato existente no formato E.164, antes de gravá-los no atributo **msRTCSIP-line**.

  - Se a sua organização não impõe um formato padrão aos números de telefone dos Serviços de Domínio Active Directory, o script deverá definir regras de normalização apropriadas para converter os números de telefone principais dos vários formatos existentes no formato E.164, antes de gravá-los no atributo **msRTCSIP-line**.

Seu script também deverá inserir o prefixo **Tel:** antes de cada número principal antes de gravá-lo no atributo **msRTCSIP-line**.

O formato esperado do número especificado nesse atributo é:

  - Tel: + 14255550100; ext = 50100.

  - Tel:5550100 (para ramais exclusivos na empresa toda).
    
    <div>
    

    > [!IMPORTANT]  
    > A normalização realizada pelo ABS (Serviço de Catálogo de Endereços) não substitui nem elimina a necessidade de normalizar o número de telefone principal de cada usuário nos Serviços de Domínio Active Directory, pois o ABS não tem acesso aos Serviços de Domínio Active Directory e, portanto, não pode copiar números de telefone principais para o atributo <STRONG>msRTCSIP-line</STRONG>.

    
    </div>

</div>

<div>

## <a name="step-2-enable-users-for-enterprise-voice"></a>Etapa 2. Habilitar usuários para o Enterprise Voice

Além de identificar os usuários que devem ser habilitados, nenhum outro planejamento especial é necessário para concluir esta etapa.

</div>

<div>

## <a name="step-3-prepare-dial-plans-for-users"></a>Etapa 3. Preparar planos de discagem para os usuários.

Usuários que estão habilitados para o Enterprise Voice não conseguirão fazer chamadas para o PSTN sem planos de discagem. Um plano de discagem é um conjunto nomeado de regras de normalização que converte números de telefone de um local nomeado, usuário individual ou objeto de contato em um formato padrão único (E.164) para fins de roteamento de chamadas e autorização. Regras de normalização definem como números de telefone expressos em vários formatos serão roteados para cada local, usuário ou objeto de contato especificado.

Para obter informações sobre como preparar planos de discagem, consulte [Dial Plans and Normalization Rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md).

</div>

<div>

## <a name="step-4-plan-user-voice-policies"></a>Etapa 4. Planejar as políticas de voz dos usuários

Configurações de serviço de classe do usuário em um PBX herdado, como o direito de fazer chamadas de longa distância ou internacionais a partir dos telefones da empresa, devem ser reconfigurados como políticas de VoIP para usuários movidos para o Enterprise Voice. Para obter detalhes sobre como planejar e criar políticas para o Enterprise Voice, consulte [Voice Policies in Lync Server 2013](lync-server-2013-voice-policies.md).

</div>

<div>

## <a name="step-5-plan-outbound-call-routes"></a>Etapa 5. Planejar rotas de chamadas de saída

As rotas de chamada especificam como o Lync Server trata as chamadas de saída feitas por usuários do Enterprise Voice. Quando um usuário disca para um número, o servidor, se necessário, normaliza a cadeia de caracteres de discagem para o formato E.164 e tenta compará-lo com um URI de SIP. Se o servidor não conseguir a correspondência, aplica o roteamento de chamada de saída com base no número. A etapa final em definir a lógica é criar uma rota de chamada nomeada separada para cada conjunto de números de telefone de destino que esteja listado em cada plano de discagem.

Para obter detalhes sobre como planejar rotas de chamada, consulte [rotas de voz no Lync Server 2013](lync-server-2013-voice-routes.md).

</div>

<div>

## <a name="step-6-configure-pbx-or-sip-trunk-to-reroute-calls-for-enterprise-voice-users"></a>Etapa 6. Configurar o PBX ou Tronco SIP para rerotear chamadas para usuários do Enterprise Voice

Usuários que anteriormente eram hospedados em uma conexão PBX ou Tronco SIP tradicional com um Provedor de Serviços de Telefonia de Internet (ITSP) mantêm seus números de telefone depois da mudança. O único requisito é que após a movimentação, o PBX ou tronco SIP deve ser reconfigurado para rotear as chamadas de entrada para usuários do Enterprise Voice para o servidor de mediação.

</div>

<div>

## <a name="step-7-move-users-to-exchange-unified-messaging-recommended"></a>Etapa 7. Mover usuários para a Unificação de Mensagens do Exchange (recomendado)

Mover usuários para a Unificação de Mensagens do Exchange consiste das seguintes tarefas:

  - Configure a Unificação de mensagens do Exchange e o Lync Server para trabalhar juntos.

  - Habilitar os usuários para atender chamadas pela Unificação de Mensagens do Exchange e para o Outlook Voice Access. Esta tarefa é executada no servidor de Unificação de Mensagens do Exchange. Para obter detalhes, consulte a Biblioteca TechNet do Exchange Server 2010 em [https://go.microsoft.com/fwlink/p/?linkID=139372](https://go.microsoft.com/fwlink/p/?linkid=139372) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

