---
title: 'Lync Server 2013: visão geral do recurso de recebimento de chamadas em grupo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Group Call Pickup
ms:assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945623(v=OCS.15)
ms:contentKeyID: 51541466
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0efc85b28a689b43d024d9996211a70dcd91cee0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755545"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-group-call-pickup-in-lync-server-2013"></a>Visão geral da retirada de chamadas em grupo no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-12_

Recebimento de chamadas em grupo, um novo recurso em atualizações cumulativas para o Lync Server 2013:2013 de fevereiro, permite que os usuários atendam às chamadas recebidas para seus colegas pelos próprios telefones. Esse novo recurso aumenta a disponibilidade de uma linha de usuário permitindo que outros usuários atendam a uma chamada de entrada discando um número de grupo de recebimento de chamadas. Quando o recebimento de chamadas em grupo é implantado, o número de chamadas de entrada direcionadas para o correio de voz pode ser reduzido significativamente, o que é especialmente útil para chamadas de clientes externos à sua organização.

O recurso de recebimento de chamadas em grupo foi projetado especificamente para unidades de negócios em ambientes abertos do Office. Chamadas de entrada não perturbam porque tocam somente no destino desejado. Porém, outros usuários que escutam o toque podem atender a chamada simplesmente discando o número de grupo de atendimento de chamadas.

Em ambientes em que os usuários não estão localizados em um layout de escritório aberto ou em que os usuários que compartilham uma responsabilidade comum estão espalhados geograficamente, a chamada em equipe apresenta-se como a solução mais adequada. A principal diferença entre o recebimento de chamadas em grupo e a chamada de equipe é que, com o recebimento de chamadas em grupo, uma chamada de entrada tocará somente no destino pretendido, mas qualquer pessoa ainda poderá atendê-la ao discar um número de grupo. Com chamada em equipe, a chamada toca nos telefones de todos os membros da equipe e qualquer usuário na equipe pode atender o telefone para responder à chamada. Uma diferença adicional entre o recebimento de chamadas em grupo e a chamada de equipe é que o recebimento de chamadas em grupo é gerenciado por um administrador, por meio do Lync Server. Com a chamada de equipe, os usuários finais gerenciam o recurso usando o cliente do Lync. Com o recebimento de chamadas em grupo, esse aspecto do gerenciamento de chamadas pode ser centralizado.

O recebimento de chamadas em grupo foi criado no aplicativo de estacionamento de chamadas. Ao implantar o recurso de recebimento de chamadas em grupo, configure a tabela órbita do estacionamento de chamada com intervalos separados de números de ramal designados como números de grupo de retirada de chamadas. Como os números de órbita de estacionamento de chamadas, os números de grupo de atendimento de chamadas precisam ser extensões virtuais que não têm um usuário ou telefone atribuídos a elas. Cada pool de front-ends onde você implanta o recebimento de chamadas em grupo pode ter um ou mais intervalos de números de grupo de recebimento de chamadas. Os intervalos de números de grupo devem ser globalmente exclusivos na implantação do Lync Server.

<div>


> [!NOTE]  
> Os intervalos de números que são designados como números de recebimento de chamadas em grupo na tabela órbita do parque de chamadas não podem ser gerenciados ou exibidos usando o painel de controle do Lync Server. A única maneira de ver todos os intervalos de números na tabela órbita do estacionamento de chamada é usar o Shell de gerenciamento do Lync Server. Da mesma forma, a única maneira de adicionar, modificar ou remover números de recebimento de chamadas em grupo é usar o Shell de gerenciamento do Lync Server.



</div>

Após você configurar os números de grupos de atendimento de chamadas, você atribui usuários a um grupo de atendimento de chamadas. Qualquer usuário que for atribuído a um grupo de atendimento de chamadas pode ter suas chamadas atendidas por outros usuários. Quando uma chamada chega para um usuário atribuído a um grupo de atendimento de chamadas, qualquer outro usuário que perceba a chamada pode atendê-la manualmente discando o número de grupo de atendimento de chamadas. O usuário que atender a chamada não precisa ser um membro do grupo. Quando uma chamada é atendida por outro usuário, uma notificação é enviada ao número que foi chamado originalmente.

<div>


> [!NOTE]  
> Um usuário pode ser membro de somente um grupo de atendimento de chamadas.



</div>

<div>


> [!NOTE]  
> Embora qualquer usuário na implantação do Lync Server possa atender a uma chamada para um membro do grupo de recebimento de chamadas, a pessoa que atende a chamada precisa saber o número correto de grupo de recebimento de chamadas para discar.



</div>

Se um usuário discar um número de grupo de atendimento de chamadas para atender uma chamada quando diversos telefones no grupo estiverem tocando, o usuário atenderá a chamada que estiver tocando a mais tempo.

Configurações de toque simultâneo funcionarão para usuários habilitados para atendimento de chamadas em grupo. Ou seja, uma chamada feita para um usuário que tem o recurso de chamada em grupo tocará para todos os destinos configurados e outro usuário poderá atender a chamada. A exceção para essa regra é quando o usuário configura toque simultâneo para todos os membros da equipe.

Não é possível usar o recurso de recebimento de chamadas em grupo para atender aos seguintes tipos de chamadas:

  - Chamadas a uma linha privada

  - Chamadas de um contato ao qual foi atribuída a política de privacidade Amigos e Família
    
    <div>
    

    > [!TIP]  
    > Um usuário que é membro de um grupo de recebimento de chamadas pode impedir que determinadas chamadas sejam recuperadas por meio da passagem de chamadas em grupo, marcando o contato como um contato pessoal no cliente do Lync. Para marcar um contato como seu contato pessoal, defina a Relação de Privacidade para o contato como Amigos e Família. Qualquer chamada de entrada de contatos com a relação de privacidade definida como amigos e parentes não pode ser recuperada usando a retirada de chamadas em grupo.

    
    </div>

  - Porção de vídeo de chamadas de áudio/vídeo
    
    <div>
    

    > [!NOTE]  
    > Se um usuário responde uma chamada de áudio/vídeo, ele recebe somente o áudio. Tanto a pessoa que realizou a chamada quanto a que está recebendo podem escalar a chamada para adicionar o vídeo.

    
    </div>

  - Chamadas de toque simultâneo que são direcionada para membros da equipe de atendimento de chamadas

  - Chamadas direcionadas a um representante

  - Chamadas direcionadas a um grupo de resposta

Os tipos de usuários a seguir não podem participar da retirada de chamadas em grupo. Ou seja, eles não devem ser incluídos em um grupo de recebimento de chamadas em grupo e não podem atender chamadas para usuários que tenham o recurso de recebimento de chamadas em grupo habilitado.

  - Usuários que estão hospedados em uma implantação híbrida

  - Usuários que não são hospedados em um pool do Lync Server 2013 com atualizações cumulativas do Lync Server 2013:2013 de fevereiro em uma implantação local

Se ninguém responder uma chamada destinada a um membro de um grupo de atendimento de chamadas, ela é direcionada conforme especificado nas configurações do cliente. Ou seja, a chamada vai para correio de voz e ou é direcionada para um outro destino, conforme estiver especificado nas configurações do cliente.

</div>

<span> </span>

</div>

</div>

</div>

