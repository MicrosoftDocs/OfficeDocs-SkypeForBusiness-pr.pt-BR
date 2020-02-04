---
title: 'Lync Server 2013: planejando linhas telefônicas privadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for private telephone lines
ms:assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412728(v=OCS.15)
ms:contentKeyID: 48184909
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0df93d8a8de73a3119e7ca9a1a7abd76e9157a17
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725311"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-private-telephone-lines-with-lync-server-2013"></a>Planejando linhas telefônicas particulares com o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-11_

O Lync Server 2013 introduz a capacidade de oferecer aos usuários uma segunda linha telefônica privada, além da linha telefônica principal. Linhas telefônicas privadas são frequentemente atribuídas a executivos e a outras pessoas que desejam um número de telefone não listado e através do qual podem ser diretamente contatados.

Linhas telefônicas privadas só podem ser configuradas com o Shell de gerenciamento do Lync Server. Você não pode configurar linhas telefônicas privadas com o painel de controle do Lync Server. Linhas telefônicas privadas devem ser configuradas apenas em implantações do Lync Server e não em implantações mistas.

<div>

## <a name="characteristics-of-private-telephone-lines"></a>Características das linhas telefônicas privadas

Embora o conceito de uma linha telefônica privada, secundária, seja fundamentalmente simples, é importante compreender as características das linhas privadas e as formas em que são similares e diferentes das linhas telefônicas principais dos usuários.

<div>

## <a name="general-characteristics-of-private-telephone-lines"></a>Características gerais das linhas telefônicas privadas

  - Um usuário pode ter somente uma linha telefônica privada.

  - Um usuário com uma linha telefônica privada só possui uma caixa postal e recebe notificações de chamadas perdidas em um único endereço de e-mail.

  - Um usuário com uma linha telefônica privada não possui um segundo endereço SIP e uma linha telefônica privada secundária não dá a ele uma segunda presença na rede (como uma segunda identidade no sistema de mensagens instantâneas).

  - Linhas telefônicas privadas estão disponíveis somente para implantações locais. Eles não estão disponíveis em implantações hospedadas do Lync Server.

</div>

<div>

## <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a>Como linhas telefônicas privadas diferem de linhas telefônicas principais

  - Os números de telefone para linhas telefônicas privadas não aparecem nos diretórios telefônicos ou listas de Contatos derivados dos Serviços de Domínio do Active Directory.

  - Nenhum dos recursos a seguir está disponível com uma linha telefônica privada: encaminhamento de chamadas, chamada de equipe, delegação, toque de equipe, recebimento de chamadas de grupo e aplicativo Grupo de Resposta.

  - Chamadas para uma linha telefônica privada têm um toque especial e a notificação do sistema para as chamadas diz ao usuário que a chamada de entrada está em sua linha privada.

  - Chamadas para a linha telefônica privada sempre tocam. Elas não seguem as regras "não incomodar".

  - Linhas telefônicas privadas são somente de entrada e não podem ser usadas para fazer chamadas de saída. Quando um usuário com uma linha telefônica privada faz uma ligação, a chamada é originada na linha telefônica principal e não oculta do receptor da chamada o nome ou o número de telefone principal do usuário.

</div>

<div>

## <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a>Como linhas telefônicas privadas são similares a linhas telefônicas principais

  - Chamadas não atendidas para uma linha telefônica privada são roteadas para a mesma caixa postal da linha telefônica principal (se a caixa postal estiver habilitada).

  - O estacionamento e o recebimento de chamadas funcionam com linhas telefônicas privadas exatamente da mesma forma como na linha telefônica principal do usuário.

  - Quando o toque simultâneo está habilitado na linha telefônica principal de um usuário, também está habilitado na linha telefônica privada.

  - O número de telefone para uma linha telefônica privada é gravado no registro de detalhes de chamada da mesma maneira que o número de telefone para a linha telefônica principal de um usuário, mas com uma indicação de que é um número telefônico privado.

  - Depois que o usuário atende uma chamada na linha telefônica privada, ela é tratada da mesma forma como se estivesse na linha telefônica principal. Por exemplo, se um usuário que recebe uma chamada em uma linha telefônica particular encaminhar a chamada ou convidar outras pessoas para uma chamada em conferência, o nome do usuário aparecerá no Lync 2013, e o número de telefone da linha telefônica principal do usuário aparecerá em identificação de chamadas.

  - Um usuário pode desviar uma chamada (redirecionar para outro destino, como um telefone celular ou residencial, antes de atender) a partir da linha telefônica privada da mesma maneira como o faria com uma linha telefônica principal.
    
    <div>
    

    > [!NOTE]  
    > Quando uma chamada para uma linha privada é roteada para um número de telefone alternativo, o número para a linha telefônica privada é disponibilizado para o número de telefone alternativo e pode ser exibido nos logs para aquele número.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Chamadas a partir de uma conferência para a linha telefônica privada não terão uma indicação de <EM>linha privada</EM> na notificação do sistema de entrada.

    
    </div>

</div>

</div>

<div>

## <a name="administering-private-telephone-lines"></a>Como administrar linhas telefônicas privadas

Além dos aspectos técnicos da criação e gerenciamento de linhas telefônicas privadas, você precisará estabelecer procedimentos administrativos para elas. Isso inclui determinar políticas para quem na organização está elegível para uma linha privada, criar e manter listas de pessoas e suas linhas telefônicas, possivelmente criar um diretório de telefonia privada para executivos, providenciar o treinamento dos usuários e tarefas relacionadas.

<div>


> [!NOTE]  
> A linha telefônica privada é armazenada no Active Directory como um atributo msRTCSIP-PrivateLine no objeto do usuário. Por padrão, qualquer membro do grupo Usuários Autenticados tem acesso de leitura a este atributo.



</div>

<div>

## <a name="assigning-telephone-numbers"></a>Como atribuir números de telefone

As contas de novos usuários que precisam de linhas de telefone particulares são criadas da mesma maneira que as contas sem linhas telefônicas particulares, usando o painel de controle do Lync Server ou o Shell de gerenciamento do Lync Server.

Use o cmdlet **set-CsUser** no Shell de gerenciamento do Lync Server para atribuir um número de telefone a uma linha telefônica privada para um usuário, por exemplo, **set-CsUser-Identity "SIP:Joe@contoso.com"-Privatee "Tel: + 14255551212"**.

Os números de telefone das linhas telefônicas privadas podem ter entre 3 e 15 números de comprimento e devem ser precedidos do prefixo "TEL:". Podem ter qualquer código de área e qualquer código de país/região, desde que sua organização tenha discagem interna direta para aquele código de área e código de país/região.

Para obter detalhes sobre cmdlets e o Shell de gerenciamento do Lync Server, consulte a documentação do [Shell de gerenciamento do Lync server 2013](lync-server-2013-lync-server-management-shell.md) .

</div>

<div>

## <a name="private-telephone-lines-in-mixed-deployments"></a>Linhas telefônicas privadas em implantações mistas

Linhas telefônicas privadas devem ser configuradas apenas para implantações do Lync Server. Em uma implantação em que há o Lync Server e o Office Communications Server 2007 ou o Office Communications Server 2007 R2 Server, quando um usuário em uma versão anterior tenta chamar uma linha telefônica particular, o roteamento da chamada falha porque o servidor não pode executar uma pesquisa de número reverso em uma linha de telefone particular.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

