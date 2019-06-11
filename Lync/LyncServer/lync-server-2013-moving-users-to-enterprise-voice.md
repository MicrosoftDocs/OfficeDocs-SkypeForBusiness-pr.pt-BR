---
title: 'Lync Server 2013: Movendo usuários para o Enterprise Voice'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Moving users to Enterprise Voice
ms:assetid: a2df6d51-5cf2-4d3e-8f97-496af5fd5e5e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412758(v=OCS.15)
ms:contentKeyID: 48184958
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1127bd0c767da7f02df8aefb30fda41a64bd353a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826735"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-users-to-enterprise-voice-in-lync-server-2013"></a>Movendo usuários para o Enterprise Voice no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-18_

Se você estiver movendo usuários de uma infraestrutura de telefonia PBX existente para o Enterprise Voice, o processo de implantação incluirá algumas etapas que não fazem parte do processo de planejamento já descrito no [Planning for Enterprise Voice no Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md). Para obter informações sobre a migração de usuários de uma implantação de voz empresarial anterior, consulte os documentos de migração que foram incluídos na mídia de instalação.

O processo de mover os usuários de uma infraestrutura de telefonia existente para o Enterprise Voice consiste nas seguintes etapas:

1.  Designar números de telefone primários.

2.  Habilite usuários para o Enterprise Voice.

3.  Preparar planos de discagem para usuários.

4.  Planejar políticas de voz de usuários.

5.  Planejar roteiros de chamadas.

6.  Configure o tronco PBX ou SIP para redirecionar chamadas para usuários habilitados para o Enterprise Voice.

7.  Mover usuários para a UM (recomendado) Exchange Unified Messaging (recomendado).

Este tópico descreve o planejamento necessário para cada uma dessas etapas.

<div>

## <a name="step-1-designate-primary-phone-numbers"></a>Etapa 1. Designar números de telefone principais

O Enterprise Voice integra voz com outras mídias de mensagens, de forma que, quando uma chamada de entrada chega ao servidor, o servidor mapeia o número para o SIP-URI do usuário e, em seguida, bifurca a chamada para todos os pontos de extremidade do cliente associados ao SIP-URI. Esse processo requer que cada usuário seja associado a um número de telefone principal.

Um número de telefone principal deve ser:

  - Globalmente exclusivo ou, no caso de extensões internas, exclusivas da empresa.

  - Pertencente à empresa e roteável na empresa. Números pessoais não devem ser usados.

Os usuários da empresa podem ter dois ou mais números de telefone listados para eles nos serviços de domínio Active Directory. Todos os números de telefone associados a um usuário específico podem ser exibidos ou alterados na folha de propriedades desse usuário no snap-in usuários e computadores do Active Directory.

A caixa **número de telefone** na guia **geral** da caixa de diálogo Propriedades do **usuário** deve conter o número do trabalho principal do usuário. Esse número normalmente será designado como o número de telefone principal do usuário.

Alguns usuários podem ter requisitos especiais (por exemplo, um executivo que deseja todas as chamadas de entrada roteadas por meio de um assistente administrativo), mas essas exceções devem ser limitadas apenas àqueles em que a necessidade é clara e crítica.

Depois que um número principal é escolhido, ele deve ser:

  - Normal para o formato E. 164, sempre que possível.

  - Copiado para o atributo de **linha msRTCSIP** do Active Directory.
    
    <div>
    

    > [!NOTE]  
    > <STRONG>Coexistente com controle de chamada remota (RCC)</STRONG><BR>O RCC é a capacidade de usar o Lync Server para monitorar e controlar um telefone PBX de área de trabalho. O controle é roteado pelo servidor, que atua como um gateway para o PBX. Embora você não possa configurar um usuário para RCC e Enterprise Voice, a configuração de URI de linha designa o número de telefone principal de um usuário em ambos os casos.<BR>Se você tiver uma infraestrutura de PBX existente que deseja que os usuários selecionados continuem a usar, você pode introduzir o Enterprise Voice em incrementos em sua organização. Para obter detalhes sobre esse cenário de implantação, consulte <A href="lync-server-2013-direct-sip-deployment-options.md">Opções de implantação de SIP direto no Lync Server 2013</A> na documentação de planejamento.<BR>Em versões anteriores, você pode habilitar o RCC e o Enterprise Voice para um usuário, mas somente se você também configurou o usuário para a bifurcação dupla, um recurso no qual uma chamada de entrada tocará o telefone PBX e o Communicator de um usuário simultaneamente. No Lync Server 2010, não há suporte para a bifurcação dupla.

    
    </div>

Há três métodos para preencher o atributo **msRTCSIP-line** :

  - Servidor de integração de identidades da Microsoft (recomendado)

  - A página **usuários** no painel de controle do Lync Server

Onde vários números de telefone devem ser processados, um script personalizado desenvolvido pela sua organização é a melhor opção. Dependendo de como sua organização representa números de telefone nos serviços de domínio Active Directory, o script pode ter que normalizar números de telefone primários para o formato E. 164 antes de copiá-los para o atributo de **linha de msRTCSIP** .

  - Se a sua organização mantém todos os números de telefone nos serviços de domínio Active Directory em um único formato e se esse formato for E. 164, o seu script só precisará gravar cada número de telefone principal para o atributo de **linha de msRTCSIP** .

  - Se a sua organização mantém todos os números de telefone nos serviços de domínio Active Directory em um único formato, mas esse formato não é E. 164, o script deve definir uma regra de normalização apropriada para converter os números de telefone principais do formato existente para E. 164 antes de escrevê-los no atributo da **linha de msRTCSIP** .

  - Se a sua organização não impõe um formato padrão para números de telefone nos serviços de domínio Active Directory, o script deve definir regras de normalização adequadas para converter os números de telefone principais de seus vários formatos para o E. 164 conformidade antes Escreva os números de telefone principais para o atributo de **linha de msRTCSIP** .

O script também terá que inserir o prefixo **Tel:** antes de cada número principal antes de escrevê-lo no atributo **msRTCSIP-line** .

O formato esperado do número especificado nesse atributo é:

  - Tel: + 14255550100; ext = 50100.

  - Tel: 5550100 (para ramais de toda a empresa)
    
    <div>
    

    > [!IMPORTANT]  
    > A normalização realizada pelo serviço de catálogo de endereços (ABS) não substitui ou, de outra forma, elimina a necessidade de normalizar o número de telefone principal de cada usuário nos serviços de domínio Active Directory porque o ABS não tem acesso aos serviços de domínio do Active Directory e Portanto, não é possível copiar números primários para o atributo de <STRONG>linha de msRTCSIP</STRONG> .

    
    </div>

</div>

<div>

## <a name="step-2-enable-users-for-enterprise-voice"></a>Etapa 2. Habilitar usuários para Enterprise Voice

Além de identificar quais usuários devem ser habilitados, não é necessário um planejamento especial para concluir esta etapa.

</div>

<div>

## <a name="step-3-prepare-dial-plans-for-users"></a>Etapa 3. Preparar planos de discagem para usuários.

Os usuários habilitados para o Enterprise Voice não poderão fazer chamadas para a PSTN sem planos de discagem no lugar. Um plano de discagem é um conjunto nomeado de regras de normalização que converte números de telefone de um local nomeado, usuário individual ou objeto de contato em um único formato padrão (E.164) para fins de roteamento de chamadas e autorização de telefones. As regras de normalização definem como os números de telefone expressos em vários formatos devem ser roteados para cada local, usuário ou objeto de contato especificado.

Para obter informações sobre como preparar planos de discagem, consulte [planos de discagem e regras de normalização no Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md).

</div>

<div>

## <a name="step-4-plan-user-voice-policies"></a>Etapa 4. Planejar políticas de voz do usuário

As configurações de classe de serviço de usuário em um PBX herdado, como o direito de fazer chamadas interurbanas ou internacionais de telefones da empresa, devem ser reconfiguradas como políticas de VoIP para usuários migrados para o Enterprise Voice. Para obter detalhes sobre como planejar e criar políticas para o Enterprise Voice, consulte [políticas de voz no Lync Server 2013](lync-server-2013-voice-policies.md).

</div>

<div>

## <a name="step-5-plan-outbound-call-routes"></a>Etapa 5. Planejar roteiros de chamadas de saída

As rotas de chamadas especificam como o Lync Server manipula chamadas feitas por usuários do Enterprise Voice. Quando um usuário disca um número, o servidor, se necessário, normaliza a cadeia de caracteres de discagem para o formato e. 164 e tenta-lo com um URI SIP. Se o servidor não puder fazer a correspondência, ele aplicará uma lógica de roteamento de chamadas de saída com base no número. A etapa final em definir essa lógica é criar uma rota de chamada nomeada separada para cada conjunto de números de telefone de destino listados em cada plano de discagem.

Para obter detalhes sobre o planejamento de rotas de chamadas, consulte [rotas de voz no Lync Server 2013](lync-server-2013-voice-routes.md).

</div>

<div>

## <a name="step-6-configure-pbx-or-sip-trunk-to-reroute-calls-for-enterprise-voice-users"></a>Etapa 6. Configurar o tronco PBX ou SIP para redirecionar chamadas para usuários do Enterprise Voice

Os usuários que anteriormente eram hospedados em um PBX tradicional ou em uma conexão de tronco SIP com um provedor de serviços de telefonia pela Internet (ITSP) mantêm seus números de telefone após a mudança. O único requisito é que, após a movimentação, o PBX ou o tronco SIP devem ser reconfigurados para direcionar as chamadas de entrada para usuários do Enterprise Voice para o servidor de mediação.

</div>

<div>

## <a name="step-7-move-users-to-exchange-unified-messaging-recommended"></a>Etapa 7. Mover usuários para a Unificação de mensagens do Exchange (recomendado)

Mover usuários para a Unificação de mensagens do Exchange consiste nas seguintes tarefas:

  - Configure a Unificação de mensagens do Exchange e o Lync Server para trabalhar em conjunto.

  - Habilite os usuários para atendimento de chamada de Unificação de mensagens do Exchange e Outlook Voice Access. Esta tarefa é executada no servidor de Unificação de mensagens do Exchange. Para obter detalhes, consulte a biblioteca do TechNet do Exchange [http://go.microsoft.com/fwlink/p/?linkID=139372](http://go.microsoft.com/fwlink/p/?linkid=139372)Server 2010 em.

</div>

</div>

<span> </span>

</div>

</div>

</div>

