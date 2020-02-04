---
title: 'Lync Server 2013: Definindo seus requisitos para conferência'
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
ms.openlocfilehash: c19269ef06fc2aa7ec19e2ede53f406b345536b3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739951"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-conferencing-in-lync-server-2013"></a>Definindo seus requisitos para conferência no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-30_

Ao determinar quais funcionalidades de conferência serão implantadas, você precisa considerar os recursos que deseja disponibilizar para seus usuários, bem como seus recursos de largura de banda de rede. A lista de perguntas a seguir orienta você pelo processo de planejamento de conferência para determinar quais recursos de conferência você deve implantar com base nas necessidades da sua organização.

  - **Você deseja habilitar a webconferência, que inclui a colaboração em documentos e o compartilhamento de aplicativos?**
    
    Em caso afirmativo, você deve habilitar a conferência para seu pool de front-end no Microsoft Lync Server 2013, ferramenta de planejamento ou no construtor de topologias. Ao habilitar a conferência, habilite A conferência via Web e conferência A/V.
    
    O compartilhamento de aplicativos requer e usa mais largura de banda que a colaboração em documentos. O Lync Server 2013 fornece um mecanismo de limitação para controlar cada sessão de compartilhamento de aplicativo. Por padrão, isso é definido como 1,5 KB por segundo para cada sessão.
    
    Se você não quiser habilitar o compartilhamento de aplicativos, mas quiser a colaboração de documentos, poderá habilitar a conferência e usar políticas de reunião para desabilitar o compartilhamento de aplicativos. Para obter detalhes sobre como configurar políticas de reunião, consulte [políticas de conferência no Lync Server 2013](lync-server-2013-conferencing-policies.md).
    
    Para habilitar os usuários a compartilharem apresentações do PowerPoint, é preciso configurar o Servidor do Office Web Apps. Para obter detalhes sobre como configurar o servidor do Office Web Apps, consulte [Configurando a integração com o servidor do Office Web Apps e o Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

  - **Você deseja habilitar A conferência A/V?**
    
    Em caso afirmativo, você deve habilitar a conferência para seu pool de front-end no Lync Server 2013, ferramenta de planejamento ou no construtor de topologias. Ao habilitar a conferência, habilite A conferência via Web e conferência A/V.
    
    A conferência A/V requer e usa mais largura de banda de rede do que a Webconferência (que inclui colaboração de documentos e compartilhamento de aplicativos). Se você não quiser habilitar uma conferência de A/V, mas quiser habilitar a conferência pela Web, poderá habilitar A conferência e usar políticas de reunião para desabilitar conferências A/V.
    
    Se quiser habilitar conferências de áudio, mas não videoconferências, você pode habilitar A conferência A/V e usar políticas de reunião para impedir videoconferências. Como alternativa, você pode habilitar a conferência A/V e permitir que somente determinados usuários iniciem ou participem de conferências A/V.
    
    <div>
    

    > [!NOTE]  
    > O Enterprise Voice não é necessário para você usar a conferência A/V. Se você habilitar a conferência A/V, seus usuários poderão adicionar áudio às conferências, caso tenham dispositivos de áudio, mesmo que você use um sistema PBX como solução de telefonia.

    
    </div>

  - **Deseja permitir que os usuários ingressem na parte de áudio de conferências ao usar um telefone PSTN?**
    
    Em caso afirmativo, implante e habilite a conferência de discagem. Em seguida, os usuários convidados (dentro e fora da sua organização) poderão ingressar na parte de áudio de conferências usando um telefone PSTN.

  - **Deseja permitir que usuários externos com clientes do Lync Server 2013 ingressem nos tipos de conferências que você ativou?**
    
    Nesse caso, você deve implantar os servidores de borda. Ao permitir a participação externa em reuniões, você maximiza o seu investimento no Lync Server 2013. Por exemplo, os usuários com laptops com o Lync Server 2013 podem participar de conferências de onde quer que estejam, em casa, no aeroporto ou em sites de clientes.
    
    Além disso, com os servidores de Borda implantados, você pode criar relações federadas com outras organizações, como clientes ou fornecedores, e os usuários dessas organizações podem colaborar com mais facilidade com seus usuários.
    
    Para obter detalhes sobre a implantação de servidores de borda, consulte [planejando o acesso de usuários externos no Lync server 2013](lync-server-2013-planning-for-external-user-access.md) e [implantando o acesso de usuários externos no Lync Server 2013](lync-server-2013-deploying-external-user-access.md). Para obter detalhes sobre como habilitar o acesso externo para o Office Web Apps Server, consulte [publicando o servidor do Office Web Apps no Lync Server 2013 usando um servidor proxy reverso](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md).

  - **Você deseja controlar os clientes que podem ingressar em reuniões do Lync Server 2013?**
    
    Em caso afirmativo, você deve configurar a página de ingresso na reunião para que apenas as opções do cliente que você deseja oferecer fiquem disponíveis. Sempre que um usuário clica em um link para ingressar em uma reunião agendada, o Lync Server 2013 detecta se um cliente já está instalado no computador. Em seguida, ele iniciará o cliente padrão e abrirá a página de ingresso na reunião, que contém links para clientes alternativos. A página Associação de reunião sempre contém a opção para usar o Microsoft Lync Web App. Além dessa opção, você pode decidir se deseja incluir links para o Atendedor e versões anteriores do Communicator. Para obter detalhes, consulte [Configurando a página ingressar na reunião no Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md).

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Requisitos da webconferência no Lync Server 2013](lync-server-2013-web-conferencing-requirements.md)

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

