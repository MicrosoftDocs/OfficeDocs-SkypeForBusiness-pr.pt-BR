---
title: 'Lync Server 2013: Configurando o convite para a reunião'
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
ms.openlocfilehash: 14e0614ecdaa73a886429e89618cac568d620938
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734641"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-meeting-invitation-in-lync-server-2013"></a>Configurando o convite da reunião no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-07-16_

Você pode personalizar convites de reunião enviados pelo suplemento de reunião online para o Lync 2013, incluindo os seguintes itens opcionais no corpo do convite da reunião:

  - **O logotipo da sua organização** Adicione o logotipo da sua organização aos convites para reunião usando a opção de URL do logotipo. Se os convites para reuniões forem enviados para pessoas de fora da sua organização, a imagem deverá estar localizada em uma URL disponível publicamente. Os formatos de imagem com suporte são GIF e JPG. Embora o Lync Server 2013 armazene a URL sem restrições de tamanho na imagem, para obter os melhores resultados, o tamanho máximo da imagem deve ter 30 pixels de altura por 188 pixels de largura.

  - **Um link de ajuda ou suporte personalizado** Adicione uma URL para o site de ajuda ou de equipe de suporte da sua organização. Se os convites para reuniões forem enviados para pessoas de fora da sua organização, a URL deverá estar disponível publicamente. O tamanho máximo da URL é 1 KB.

  - **Texto de isenção de responsabilidade legal** Adicione uma URL para o texto legal ou um aviso de isenção de responsabilidade que será exibido em todos os convites da reunião. Se os convites para reuniões forem enviados para pessoas de fora da sua organização, a URL deverá estar disponível publicamente. O tamanho máximo da URL é 1 KB.

  - **Texto do rodapé personalizado** Adicione o texto que será renderizado como um rodapé personalizado no convite. O comprimento máximo do texto que pode ser adicionado é 2 KB.

Você pode configurar essas opções usando o painel de controle do Lync Server ou o Shell de gerenciamento do Lync Server.

<div>


**Para personalizar o convite da reunião usando o painel de controle do Lync Server**

1.  Em uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **conferência** e em **configuração de reunião**.

4.  Na página **Configuração de reunião**, clique em **Novo** e siga um destes procedimentos:
    
      - Para criar uma política a nível local, clique em **Configuração local**. No campo de pesquisa **Selecionar um local**, digite todo ou parte do nome do local para o qual você deseja definir as configurações de participação de reunião. Na lista resultante de locais, clique no local desejado e, em seguida, clique em **OK**.
    
      - Para criar uma política a nível de pool, clique em **Configuração do pool**. No campo de pesquisa **Selecionar um serviço**, digite todo ou parte do nome do serviço do pool para o qual você deseja definir as configurações de participação de reunião. Na lista resultante de serviços, clique no pool desejado e, em seguida, clique em **OK**.

5.  Execute qualquer uma das seguintes ações:
    
      - No campo **URL do logotipo** , digite a URL da imagem de logotipo da sua organização.
    
      - No campo **URL da ajuda** , digite a URL do site de ajuda ou suporte da sua organização.
    
      - No campo **texto legal** , digite a URL do texto legal ou da isenção de responsabilidade que você deseja incluir em convites de reunião.
    
      - No campo **texto do rodapé personalizado** , digite o texto do rodapé, até 2 KB.

**Para personalizar o convite da reunião usando o Shell de gerenciamento do Lync Server**

1.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

2.  Execute o cmdlet **New-CsMeetingConfiguration** ou **set-CsMeetingConfiguration** para criar ou configurar as opções de convite da reunião. Por exemplo, execute:
    
        New-CsMeetingConfiguration -Identity site:Redmond -LogoURL "http://www.contoso.com/logo/contosobanner.gif" -HelpURL "http://www.contoso.com/support" -LegalURL "http://www.contoso.com/disclaimer" -CustomFooterText "Communications may be monitored or recorded."

</div>

</div>

<span> </span>

</div>

</div>

</div>

