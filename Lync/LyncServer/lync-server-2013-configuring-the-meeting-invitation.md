---
title: 'Lync Server 2013: Configurando o convite da reunião'
description: 'Lync Server 2013: Configurando o convite da reunião.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the meeting invitation
ms:assetid: 7faa4797-0344-418b-9fa3-59dfb9c2baf7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398638(v=OCS.15)
ms:contentKeyID: 48184641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64438d7a451cb794c125207fa594e1c00b534c80
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564327"
---
# <a name="configuring-the-meeting-invitation-in-lync-server-2013"></a>Configurando o convite de reunião no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-07-16_

Você pode personalizar convites de reunião enviados pelo suplemento de reunião online para o Lync 2013, incluindo os seguintes itens opcionais no corpo do convite da reunião:

  - **O logotipo da sua organização** Adicione o logotipo da sua organização aos convites de reunião usando a opção URL do logotipo. Se os convites de reunião serão enviados para pessoas externas à sua organização, a imagem deverá estar localizada em uma URL disponível publicamente. Os formatos de imagem compatíveis são GIF e JPG. Embora o Lync Server 2013 armazene a URL sem restrições de tamanho na imagem, para obter melhores resultados, o tamanho máximo da imagem deve ter 30 pixels de altura por 188 pixels de largura.

  - **Um link de ajuda ou suporte personalizado** Adicione uma URL para o site de ajuda ou de equipe de suporte da sua organização. Se os convites para reuniões forem enviados para pessoas externas à sua organização, a URL deverá estar disponível publicamente. O tamanho máximo da URL é de 1 KB.

  - **Texto de aviso de isenção legal** Adicione uma URL para o texto legal ou um aviso de isenção de responsabilidade que será exibido em todos os convites da reunião. Se os convites para reuniões forem enviados para pessoas externas à sua organização, a URL deverá estar disponível publicamente. O tamanho máximo da URL é de 1 KB.

  - **Texto de rodapé personalizado** Adicione o texto que será renderizado como um rodapé personalizado no convite. O comprimento máximo do texto que pode ser adicionado é de 2 KB.

Você pode configurar essas opções usando o painel de controle do Lync Server ou o Shell de gerenciamento do Lync Server.

<div>


**Para personalizar o convite de reunião usando o painel de controle do Lync Server**

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Conferência** e em **Configuração da reunião**.

4.  Na página **Configuração de reunião **, clique em **Novo ** e siga um destes procedimentos:
    
      - Para criar uma política a nível local, clique em **Configuração local**. No campo de pesquisa **Selecionar um local**, digite todo ou parte do nome do local para o qual você deseja definir as configurações de participação de reunião. Na lista resultante de locais, clique no local desejado e em **OK**.
    
      - Para criar uma política a nível de pool, clique em **Configuração do pool**. No campo de pesquisa **Selecionar um serviço**, digite todo ou parte do nome do serviço do pool para o qual você deseja definir as configurações de participação de reunião. Na lista resultante de serviços, clique no pool desejado e em **OK**.

5.  Faça um dos seguintes:
    
      - No campo **URL do logotipo** , digite a URL da imagem de logotipo da sua organização.
    
      - No campo **URL da ajuda** , digite a URL do site de ajuda ou suporte da sua organização.
    
      - No campo **texto legal** , digite a URL para o texto legal ou o aviso de isenção de responsabilidade que você deseja incluir em convites de reunião.
    
      - No campo **texto do rodapé personalizado** , digite o texto do rodapé, até 2 KB.

**Para personalizar o convite de reunião usando o Shell de gerenciamento do Lync Server**

1.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

2.  Execute o cmdlet **New-CsMeetingConfiguration** ou **set-CsMeetingConfiguration** para criar ou configurar as opções de convite de reunião. Por exemplo, execute:
    
        New-CsMeetingConfiguration -Identity site:Redmond -LogoURL "http://www.contoso.com/logo/contosobanner.gif" -HelpURL "http://www.contoso.com/support" -LegalURL "http://www.contoso.com/disclaimer" -CustomFooterText "Communications may be monitored or recorded."

</div>

</div>

<span> </span>

</div>

</div>

</div>

