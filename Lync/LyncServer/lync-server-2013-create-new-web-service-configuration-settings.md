---
title: 'Lync Server 2013: criar novas definições de configuração de serviço Web'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create new Web Service configuration settings
ms:assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182605(v=OCS.15)
ms:contentKeyID: 48185801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86105e4dbf6b624f87844a68ebe5fca6bba02247
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829824"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-new-web-service-configuration-settings-in-lync-server-2013"></a>Criar novas opções de configuração de serviço Web no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

Você pode usar a página **serviço Web** para configurar os métodos de autenticação para acessar servidores Web relacionados ao Lync Server 2013 e serviços Web.

Siga estas etapas para criar a nova política de Web Service.

<div>

## <a name="to-create-new-web-service-configuration-settings"></a>Para criar novas definições de configuração de serviço da Web

1.  Em uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Segurança** e em **Serviço da Web**.

4.  Na página **Serviço da Web**, clique em **Novo** e faça um dos seguintes:
    
      - Para configurar o Serviço da Web para um site, clique em **Configuração do site**. Em **Selecionar um site**, clique em um site no qual a política de Serviço da Web será aplicada e clique em **OK**.
    
      - Para configurar o Serviço da Web para um pool, clique em **Configuração do pool**. Em **Selecionar um Serviço**, clique no serviço no qual a política de Serviço da Web será aplicada e clique em **OK**.

5.  Em **Nova configuração do Serviço da Web**, em **Autenticação integrada do Windows**, selecione **Negociar**, **Autenticação integrada do Windows** ou **Nenhum**.

6.  Selecione um ou mais dos seguintes dependendo das capacidades dos clientes e do suporte no seu ambiente:
    
      - **Habilitar autenticação de PIN** para permitir que os clientes sejam autenticados usando números PIN.
    
      - **Habilitar autenticação de certificado** para que os servidores no pool emitam certificados para os clientes.
    
      - **Habilitar download da cadeia de certificados** para que os servidores sejam apresentados com um download de certificado de autenticação da cadeia de certificados para aquele certificado.

7.  Clique em **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

