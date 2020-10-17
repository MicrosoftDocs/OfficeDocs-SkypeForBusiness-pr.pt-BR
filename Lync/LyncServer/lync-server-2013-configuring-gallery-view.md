---
title: 'Lync Server 2013: Configurando a exibição da Galeria'
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
ms.openlocfilehash: 1fd9823ca211242e0fd317e8a62ea118ed91a82f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517458"
---
# <a name="configuring-gallery-view-in-lync-server-2013"></a>Configurando o modo de exibição de galeria no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-30_

No Lync Server 2013, configure a Galeria exibir videoconferência em política de conferência. O Modo de exibição de Galeria é ativado por padrão. Se você não deseja permitir o Modo de exibição de Galeria ou deseja permitir para alguns usuários apenas, você precisa desativar esse recurso na política de conferência.

Quando o vídeo de um participante de conferência não está disponível, a experiência de exibição da Galeria de usuários pode ser aprimorada se você implantar fotos de alta resolução, um novo recurso no Lync Server 2013. As fotos de alta resolução fornecem uma alternativa para as fotos de contato de resolução menor e limitada armazenadas nos serviços de domínio do Active Directory. As fotos de alta resolução são armazenadas na caixa de correio do Exchange 2013 de um usuário e, portanto, exigem que você integre o Lync Server 2013 com o Exchange 2013. Para obter detalhes, consulte o artigo de blog NextHop, "integrando o Exchange 2013 e o Lync Server 2013" em [https://go.microsoft.com/fwlink/p/?LinkId=260987](https://go.microsoft.com/fwlink/p/?linkid=260987) .

<div>


> [!NOTE]  
> O conteúdo de cada blog e sua URL estão sujeitos a alterações sem aviso prévio.



</div>

Você pode exibir ou modificar os parâmetros de exibição da Galeria usando o painel de controle do Lync Server 2013 ou usando um dos seguintes cmdlets:

  - **Get-CsConferencingPolicy**

  - **Set-CsConferencingPolicy**

  - **New-CsConferencingPolicy**

Configure o Modo de exibição de Galeria com uma das configurações de política de conferência a seguir:

  - **AllowMultiview**     Esse parâmetro controla se um usuário tem permissão para organizar a Galeria de vídeo em conferências. Este parâmetro se aplica a reuniões programadas e ad-hoc criadas pelo usuário.
    
    Exemplos:
    
      - Esse parâmetro é definido como true para o usuário A, que é hospedado em um pool do Lync Server 2013. Reuniões organizadas pelo Usuário A permitem que os usuários participem e recebam diversos fluxos de vídeo.
    
      - Esse parâmetro é definido como false para o usuário B, que é hospedado em um pool do Lync Server 2013. As reuniões organizadas pelo usuário B têm um único fluxo de vídeo semelhante à experiência de conferência de vídeo fornecida pelo Lync Server 2010.
    
    Este parâmetro determina quem pode organizar reuniões que permitem vários fluxos de vídeo. Os participantes nas reuniões que permitem vários fluxos de vídeo podem ou não ter permissão para receber vários fluxos de vídeo, com base nas permissões individuais (consulte a descrição para o parâmetro EnableMultiviewJoin).

  - **EnableMultiviewJoin**     Esse parâmetro controla se um participante de uma reunião recebe a Galeria exibir experiência de vídeo em reuniões que permitem. Este parâmetro controla a experiência do usuário em qualquer reunião o qual ele participe.
    
    Exemplos:
    
      - Esse parâmetro é definido como true para o usuário C. o usuário C pode receber vários fluxos de vídeo ao participar de uma reunião organizada ou iniciada pelo usuário A. o usuário C recebe um único fluxo de vídeo semelhante à experiência de conferência de vídeo fornecida pelo Lync Server 2010 ao participar de uma reunião organizada ou iniciada pelo usuário B.
    
      - Esse parâmetro é definido como false para o usuário D. o usuário D recebe um único fluxo de vídeo semelhante à experiência de videoconferência fornecido pelo Lync Server 2010 ao participar de qualquer reunião organizada pelo usuário A ou usuário B.

O procedimento a seguir é um exemplo de uso do Shell de gerenciamento do Lync Server para habilitar a visualização da conferência de vídeo pela galeria.

<div>

## <a name="to-modify-conferencing-policy-for-gallery-view-video-conferencing"></a>Para modificar a política de conferência para conferência de vídeo no Modo de exibição de Galeria

1.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

2.  Na linha de comando, execute o seguinte cmdlet para editar a política de conferência:
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -AllowMultiview $true -EnableMultiviewJoin $true 

</div>

</div>

<span> </span>

</div>

</div>

</div>

