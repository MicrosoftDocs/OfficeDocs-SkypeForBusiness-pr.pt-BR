---
title: 'Lync Server 2013: Configurando o modo de exibição de galeria'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Gallery View
ms:assetid: 4a609178-47d8-4682-ac8d-29f882801924
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204871(v=OCS.15)
ms:contentKeyID: 48184069
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06054e1728245c87e8bf35419d3890f4e379543a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728841"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-gallery-view-in-lync-server-2013"></a>Configurando o modo de exibição de galeria no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-30_

No Lync Server 2013, configure a Galeria de videoconferência na política de conferência. O modo de exibição de galeria está ativado por padrão. Se você não deseja permitir o modo de exibição de galeria ou deseja permitir apenas alguns usuários, é preciso desativar o recurso na política de conferência.

Quando o vídeo de um participante da conferência não está disponível, a experiência de exibição da galeria dos usuários pode ser aprimorada se você implantar fotos de alta resolução, um novo recurso no Lync Server 2013. Fotos de alta resolução fornecem uma alternativa para as fotos de contato de resolução menor e limitada armazenadas nos serviços de domínio Active Directory. Fotos de alta resolução são armazenadas na caixa de correio do Exchange 2013 de um usuário e, portanto, exigem que você integre o Lync Server 2013 com o Exchange 2013. Para obter detalhes, consulte o artigo sobre o blog NextHop, "integrando o Exchange 2013 e o [http://go.microsoft.com/fwlink/p/?LinkId=260987](http://go.microsoft.com/fwlink/p/?linkid=260987)Lync Server 2013", em.

<div>


> [!NOTE]  
> O conteúdo de cada blog e sua URL estão sujeitos a alterações sem aviso prévio.



</div>

Você pode exibir ou modificar os parâmetros do modo de exibição de galeria usando o painel de controle do Lync Server 2013 ou usando um dos seguintes cmdlets:

  - **Get-CsConferencingPolicy**

  - **Set-CsConferencingPolicy**

  - **New-CsConferencingPolicy**

Configurar o modo de exibição de galeria com as seguintes configurações de política de conferência:

  - **AllowMultiview**   esse parâmetro controla se um usuário tem permissão para organizar a galeria e exibir conferências de vídeo. Esse parâmetro se aplica a reuniões agendadas e ad hoc criadas pelo usuário.
    
    Exemplos
    
      - Esse parâmetro é definido como true para o usuário A, que é hospedado em um pool do Lync Server 2013. Reuniões organizadas pelo usuário A permitem que os usuários ingressem e recebam vários fluxos de vídeo.
    
      - Esse parâmetro é definido como false para o usuário B, que é hospedado em um pool do Lync Server 2013. As reuniões organizadas pelo usuário B têm um único fluxo de vídeo semelhante à experiência de videoconferência fornecida pelo Lync Server 2010.
    
    Esse parâmetro determina quem pode organizar reuniões que permitem vários fluxos de vídeo. Participantes em reuniões que permitem vários fluxos de vídeo podem ou não ter permissão para receber vários fluxos de vídeo com base em suas permissões individuais (consulte a descrição para o parâmetro EnableMultiviewJoin).

  - **EnableMultiviewJoin**   esse parâmetro controla se um participante de uma reunião recebe a experiência de exibição de vídeo de galeria em reuniões que o permitem. Esse parâmetro controla a experiência do usuário em qualquer reunião na qual ele ou ela participa.
    
    Exemplos
    
      - Esse parâmetro é definido como true para o usuário C. o usuário C pode receber vários fluxos de vídeo ao participar de uma reunião organizada ou iniciada pelo usuário A. o usuário C recebe um único fluxo de vídeo semelhante à experiência de videoconferência fornecida pelo Lync Server 2010 quando participar de uma reunião organizada ou iniciada pelo usuário B.
    
      - Esse parâmetro é definido como false para o usuário D. o usuário D recebe um único fluxo de vídeo semelhante à experiência de videoconferência fornecida pelo Lync Server 2010 quando estiver participando de qualquer reunião organizada pelo usuário A ou o usuário B.

O procedimento a seguir é um exemplo de como usar o Shell de gerenciamento do Lync Server para habilitar a conferência de vídeo do modo de exibição de galeria.

<div>

## <a name="to-modify-conferencing-policy-for-gallery-view-video-conferencing"></a>Para modificar a política de conferência para a Galeria exibir videoconferência

1.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

2.  Na linha de comando, execute o seguinte cmdlet para editar a política de conferência:
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -AllowMultiview $true -EnableMultiviewJoin $true 

</div>

</div>

<span> </span>

</div>

</div>

</div>

