---
title: 'Lync Server 2013: definindo seus requisitos para conferência'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for conferencing
ms:assetid: 5c83e268-22bf-42b2-bac3-3237b5e02e03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204935(v=OCS.15)
ms:contentKeyID: 48184255
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9572317dc88d354f7df815be5dcb3cae4ffeba6b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504368"
---
# <a name="defining-your-requirements-for-conferencing-in-lync-server-2013"></a>Definindo seus requisitos de conferência no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-30_

Ao determinar quais funcionalidades de conferência serão implantadas, você precisa considerar os recursos que deseja disponibilizar para seus usuários, bem como seus recursos de largura de banda de rede. A lista de perguntas a seguir o guiará durante o processo de planejamento de conferências para determinar quais recursos de conferência você deve implantar de acordo com as necessidades de sua organização.

  - **Você deseja habilitar a webconferência, que inclui a colaboração em documentos e o compartilhamento de aplicativos?**
    
    Em caso afirmativo, você deve habilitar a conferência para seu pool de front-ends no Microsoft Lync Server 2013, na ferramenta de planejamento ou no construtor de topologias. Ao habilitar a conferência, tanto a webconferência como a conferência A/V são habilitadas.
    
    O compartilhamento de aplicativo requer e usa mais largura de banda do que a colaboração em documentos. O Lync Server 2013 fornece um mecanismo de limitação para controlar cada sessão de compartilhamento de aplicativo. Por padrão, isso é definido como 1,5 KB por segundo para cada sessão.
    
    Se você não desejar habilitar o compartilhamento de aplicativo, mas desejar a colaboração em documentos, poderá habilitar a conferência e usar políticas de reunião para desabilitar o compartilhamento de aplicativo. Para obter detalhes sobre como configurar políticas de reunião, consulte [políticas de conferência no Lync Server 2013](lync-server-2013-conferencing-policies.md).
    
    Para permitir que os usuários compartilhem apresentações do PowerPoint, você precisa configurar o servidor do Office Web Apps. Para obter detalhes sobre como configurar o servidor do Office Web Apps, consulte [Configurando a integração com o servidor do Office Web Apps e o Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

  - **Deseja habilitar a conferência A/V?**
    
    Em caso afirmativo, você deve habilitar a conferência para seu pool de front-ends no Lync Server 2013, na ferramenta de planejamento ou no construtor de topologias. Ao habilitar a conferência, tanto a webconferência como a conferência A/V são habilitadas.
    
    A conferência A/V exige e usa mais largura de banda que a webconferência (que inclui a colaboração em documentos e o compartilhamento de aplicativo). Se você desejar habilitar a webconferência, mas não a conferência A/V, poderá habilitar a conferência e usar as políticas de reunião para desabilitar a conferência A/V.
    
    Se você desejar habilitar a conferência de áudio, mas não a conferência de vídeo, poderá habilitar a conferência A/V e usar políticas de reunião para impedir as conferências de vídeo. Como alternativa, você pode habilitar a conferência A/V e permitir que somente determinados usuários iniciem ou participem de conferências A/V.
    
    <div>
    

    > [!NOTE]  
    > O Enterprise Voice não é necessário para usar A conferência A/V. Se você habilitar a conferência A/V, seus usuários poderão adicionar áudio a suas conferências se tiverem dispositivos de áudio, mesmo que você use um sistema PBX como sua solução de telefone.

    
    </div>

  - **Deseja permitir que os usuários ingressem na parte de áudio de conferências quando usam um telefone PSTN?**
    
    Em caso afirmativo, implante e habilite a conferência de discagem. Em seguida, os usuários convidados (dentro e fora da sua organização) poderão ingressar na parte de áudio de conferências usando um telefone PSTN.

  - **Deseja permitir que usuários externos com clientes do Lync Server 2013 ingressem nos tipos de conferências que você habilitou?**
    
    Em caso afirmativo, você deve implantar Servidores de Borda. Ao permitir a participação externa em reuniões, você maximiza seu investimento no Lync Server 2013. Por exemplo, os usuários com laptops com o Lync Server 2013 podem participar de conferências de onde quer que estejam, em casa, no aeroporto ou em sites do cliente.
    
    Além disso, com os Servidores de Borda implantados, você pode criar relacionamentos federados com outras organizações (como seus clientes ou fornecedores) e os usuários de empresas poderão colaborar mais facilmente com os usuários.
    
    Para obter detalhes sobre a implantação de servidores de borda, consulte [Planning for External User Access in Lync server 2013](lync-server-2013-planning-for-external-user-access.md) e [Deploying external User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md). Para obter detalhes sobre como habilitar o acesso externo para o servidor do Office Web Apps, consulte [Publishing Office Web Apps Server in Lync Server 2013 using a Reverse Proxy Server](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md).

  - **Você deseja controlar os clientes que podem ingressar em reuniões do Lync Server 2013?**
    
    Em caso afirmativo, você deve configurar a página de ingresso em reunião para que apenas as opções do cliente que você deseja oferecer fiquem disponíveis. Cada vez que um usuário clica em um link para ingressar em uma reunião agendada, o Lync Server 2013 detecta se um cliente já está instalado no computador. Em seguida, ele iniciará o cliente padrão e abrirá a página de ingresso em reunião, que contém links para clientes alternativos. A página de participação da reunião contém a opção de usar o Microsoft Lync Web App. Além dessa opção, você pode decidir se deseja incluir links para o participante e versões anteriores do Communicator. Para obter detalhes, consulte [Configurando a página de ingresso na reunião no Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md).

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Requisitos de Webconferência no Lync Server 2013](lync-server-2013-web-conferencing-requirements.md)

  - [Requisitos de conferência A/V no Lync Server 2013](lync-server-2013-a-v-conferencing-requirements.md)

  - [Requisitos de conferência discada no Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md)

</div>

<div>

## <a name="see-also"></a>Confira também


[Planejamento de conferência no Lync Server 2013](lync-server-2013-planning-for-conferencing.md)  
[Lista de verificação de implantação para conferência no Lync Server 2013](lync-server-2013-deployment-checklist-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

