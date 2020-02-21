---
title: 'Lync Server 2013: visão geral do recebimento de chamadas em grupo'
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
ms.openlocfilehash: d9001d3e89e07943915b923ec4bfa8abf2683c78
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216257"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-group-call-pickup-in-lync-server-2013"></a>Visão geral do recebimento de chamadas em grupo no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-12_

Atendimento de chamadas em grupo, um novo recurso em atualizações cumulativas do Lync Server 2013:2013 de fevereiro, permite que os usuários respondam chamadas de entrada para seus colegas de seus próprios telefones. Esse novo recurso aumenta a disponibilidade da linha de um usuário permitindo que outros usuários respondam a uma chamada de entrada discando um número de grupo de recebimento de chamada. Quando o recebimento de chamadas em grupo é implantado, o número de chamadas de entrada que são roteadas para caixa postal pode ser significativamente reduzido, o que é particularmente útil para chamadas de clientes que são externos à sua organização.

O recurso de recebimento de chamadas de grupo é projetado especificamente para unidades de negócios em ambientes abertos do Office. As chamadas de entrada não causam interrupções porque tocam apenas no destino desejado. Outros usuários que ouvirem o toque, no entanto, ainda podem pegar a chamada simplesmente discando o número do grupo.

Em ambientes em que os usuários não estão localizados em um layout de escritório aberto ou onde os usuários que compartilham uma responsabilidade comum são distribuídos geograficamente, a chamada de equipe apresenta a solução mais adequada. A principal diferença entre o recebimento de chamadas em grupo e a chamada de equipe é que, com o recebimento de chamadas de grupo, uma chamada de entrada tocará somente no destino desejado, mas qualquer pessoa ainda pode optar por respondê-la discando um número de grupo. Com a chamada em equipe, a chamada toca em todos os telefones dos membros da equipe e qualquer usuário na equipe pode pegar o telefone para responder à chamada. Uma diferença adicional entre o recebimento de chamadas em grupo e a chamada de equipe é que o recebimento de chamadas de grupo é gerenciado por um administrador, por meio do Lync Server. Com a chamada em equipe, os usuários finais gerenciam o recurso usando o cliente Lync. Com o recebimento de chamadas em grupo, esse aspecto do gerenciamento de chamadas pode ser centralizado.

O recebimento de chamadas em grupo é criado no aplicativo de estacionamento de chamada. Ao implantar o recebimento de chamadas em grupo, você configura a tabela de órbita de estacionamento de chamada com intervalos separados de números de ramal designados como números de grupo de recebimento de chamada. Como números de órbita de estacionamento de chamada, os números de grupo de recebimento de chamada devem ser extensões virtuais que não têm nenhum usuário ou telefone atribuído a eles. Cada pool de front-ends onde você implanta o recebimento de chamadas em grupo pode ter um ou mais intervalos de números de grupo de recebimento de chamada. Os intervalos de números de grupo devem ser globalmente exclusivos na implantação do Lync Server.

<div>


> [!NOTE]  
> Os intervalos de números designados como números de recebimento de chamada em grupo na tabela de órbita de estacionamento de chamadas não podem ser gerenciados ou exibidos usando o painel de controle do Lync Server. A única maneira de ver todos os intervalos de números na tabela de órbita de estacionamento de chamada é usar o Shell de gerenciamento do Lync Server. Da mesma forma, a única maneira de adicionar, modificar ou remover números de recebimento de chamadas de grupo é usar o Shell de gerenciamento do Lync Server.



</div>

Depois de configurar os números de grupo de recebimento de chamada, você atribui usuários a um grupo de recebimento de chamada. Qualquer usuário atribuído a um grupo de recebimento de chamadas pode ter suas chamadas atendidas por outros usuários. Quando uma chamada chega a um usuário atribuído a um grupo de recebimento de chamadas, qualquer outro usuário que observe a chamada pode respondê-la, discando manualmente o número do grupo de recebimento de chamada. O usuário que escolhe a chamada não precisa ser um membro do grupo. Quando uma chamada é selecionada por outro usuário, uma notificação é enviada para o número chamado originalmente.

<div>


> [!NOTE]  
> Um usuário pode ser um membro de apenas um grupo de recebimento de chamada.



</div>

<div>


> [!NOTE]  
> Embora qualquer usuário na implantação do Lync Server possa atender a uma chamada para um membro do grupo de recebimento de chamadas, a pessoa que está respondendo à chamada deve saber o número correto do grupo de recebimento de chamadas para discar.



</div>

Se um usuário discar um número de grupo de recebimento de chamada para responder a uma chamada quando vários telefones no grupo estiverem tocando, o usuário responderá à chamada que está tocando o mais longo.

As configurações de toque simultâneo funcionarão para usuários que tenham o recebimento de chamadas em grupo. Ou seja, uma chamada feita a um usuário que tenha o recebimento de chamadas de grupo tocará para todos os destinos configurados e outro usuário poderá atender à chamada. A exceção a essa regra é quando o usuário configura o toque simultâneo para chamar todos os membros da equipe.

O recebimento de chamadas em grupo não pode ser usado para atender os seguintes tipos de chamadas:

  - Chamadas para uma linha privada

  - Chamadas de um contato que recebeu a relação de privacidade de amigos e familiares
    
    <div>
    

    > [!TIP]  
    > Um usuário que seja membro de um grupo de recebimento de chamadas pode impedir que determinadas chamadas sejam recuperadas por meio do recebimento de chamadas em grupo, marcando o contato como um contato pessoal no cliente do Lync. Para marcar um contato como contato pessoal, defina a relação de privacidade do contato como amigos e família. Qualquer chamada de entrada de contatos com a relação de privacidade definida como amigos e família não pode ser recuperada usando o recebimento de chamadas em grupo.

    
    </div>

  - Parte de vídeo de chamadas de áudio/vídeo
    
    <div>
    

    > [!NOTE]  
    > Se um usuário responder a uma chamada de áudio/vídeo, o usuário receberá apenas o áudio. A pessoa que está ligando ou a pessoa que responde a chamada pode escalonar a chamada para adicionar vídeo.

    
    </div>

  - Chamadas de toque simultâneas roteadas para membros da chamada em equipe

  - Chamadas roteadas para um representante

  - Chamadas encaminhadas para um grupo de resposta

Os tipos de usuários a seguir não podem participar do recebimento de chamadas em grupo. Ou seja, eles não devem ser incluídos em um grupo de recebimento de chamadas de grupo e não podem pegar chamadas para usuários que tenham o recebimento de chamadas de grupo habilitado.

  - Usuários hospedados online em uma implantação híbrida

  - Usuários que não estão hospedados em um pool do Lync Server 2013 com atualizações cumulativas do Lync Server 2013:2013 de fevereiro em uma implantação local

Se ninguém responder uma chamada para um membro de um grupo de recebimento de chamada, a chamada será roteada conforme especificado nas configurações do cliente. Ou seja, a chamada vai para a caixa postal ou é encaminhada para um destino diferente, conforme especificado nas configurações do cliente.

</div>

<span> </span>

</div>

</div>

</div>

