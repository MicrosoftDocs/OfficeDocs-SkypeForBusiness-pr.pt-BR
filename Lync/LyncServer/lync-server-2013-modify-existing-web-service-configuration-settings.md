---
title: 'Lync Server 2013: modificar as configurações de configuração do serviço Web existentes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify existing Web Service configuration settings
ms:assetid: bd9c7aa5-d31c-4fab-b31d-8baae26b1296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182580(v=OCS.15)
ms:contentKeyID: 48185272
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11bd7f4629d4a3cf0f356a47760810e380af7deb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737131"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-existing-web-service-configuration-settings-in-lync-server-2013"></a>Modificar as configurações de serviço Web existentes no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

Você pode usar a página **serviço Web** para configurar os métodos de autenticação para acessar servidores Web relacionados ao Lync Server 2013 e serviços Web.

Execute estas etapas para modificar uma política de Serviço Web existente.

<div>

## <a name="to-modify-existing-web-service-configuration-settings"></a>Para modificar definições de configuração de Serviço da Web

1.  Em uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Segurança** e em **Serviço da Web**.

4.  Na página **Serviço da Web**, clique em uma configuração, em **Editar** e clique em **Mostrar detalhes**.

5.  Em **Editar Configuração do Serviço da Web**, em **Autenticação do Windows Integrada**, selecione **Negociar**, **NTLM** ou **Nenhum**.

6.  Selecione um ou mais dos seguintes dependendo das capacidades dos clientes e do suporte no seu ambiente:
    
      - **Habilitar autenticação de PIN** para permitir que os clientes sejam autenticados usando números PIN.
    
      - **Habilitar autenticação de certificado** para que os servidores no pool emitam certificados para os clientes.
    
      - **Habilitar download da cadeia de certificados** para que os servidores sejam apresentados com um download de certificado de autenticação da cadeia de certificados para aquele certificado.

7.  Clique em **Confirmar**.

</div>

<div>

## <a name="see-also"></a>Confira também


[Configurando autenticação no painel de controle do Lync Server 2013](lync-server-2013-configuring-authentication-in-the-lync-server-control-panel.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

