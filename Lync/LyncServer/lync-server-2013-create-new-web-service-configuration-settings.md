---
title: 'Lync Server 2013: criar novas definições de configuração do serviço Web'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create new Web Service configuration settings
ms:assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182605(v=OCS.15)
ms:contentKeyID: 48185801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d44e86ad1d587bd3dddb921cdeea3ed2a65ea26
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515568"
---
# <a name="create-new-web-service-configuration-settings-in-lync-server-2013"></a>Criar novas definições de configuração do serviço Web no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

Você pode usar a página de **serviço Web** para configurar os métodos de autenticação para acessar os servidores Web e serviços Web relacionados ao Lync Server 2013.

Siga estas etapas para criar uma nova política de serviço Web.

<div>

## <a name="to-create-new-web-service-configuration-settings"></a>Para criar novas definições de configuração de serviço da Web

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Segurança** e em **Serviço Web**.

4.  Na página **serviço Web** , clique em **novo**e siga um destes procedimentos:
    
      - Para configurar o serviço Web de um site, clique em **configuração do site**. Em **selecionar um site**, clique no site ao qual a política de serviço da Web será aplicada a um site e clique em **OK**.
    
      - Para configurar o serviço Web para um pool, clique em **configuração do pool**. Em **selecionar um serviço**, clique no serviço ao qual a política de serviço da Web será aplicada e clique em **OK**.

5.  Em **nova configuração de serviço da Web**, em **autenticação integrada do Windows**, selecione **negociar**, **autenticação integrada do Windows**ou **nenhum**.

6.  Selecione uma ou mais das seguintes opções, dependendo dos recursos dos clientes do e suporte em seu ambiente:
    
      - **Habilitar Autenticação de PIN** para permitir que os clientes sejam autenticados usando números PIN.
    
      - **Habilitar autenticação de certificado** para que os servidores no pool emitam certificados aos clientes.
    
      - **Habilitar download da cadeia de certificados** para que os servidores com um certificado de autenticação baixem a cadeia de certificados para esse certificado.

7.  Clique em **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

