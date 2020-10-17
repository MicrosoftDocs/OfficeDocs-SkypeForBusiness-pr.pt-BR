---
title: 'Lync Server 2013: Configurando o AD FS 2,0 para dar suporte à autenticação de cliente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring AD FS 2.0 to support client authentication
ms:assetid: 4d93d400-ccaa-4da8-a71b-d05d7ba79d93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308565(v=OCS.15)
ms:contentKeyID: 54973687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d2b713d109a72431e78e966258a84c084523a7a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517638"
---
# <a name="configuring-ad-fs-20-to-support-client-authentication-in-lync-server-2013"></a>Configurando o AD FS 2,0 para suportar a autenticação de cliente no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-07-03_

Há dois tipos de autenticação possíveis que podem ser configurados para permitir que o AD FS 2,0 suporte a autenticação usando cartões inteligentes:

  - Autenticação baseada em formulários (FBA)

  - Autenticação do cliente de segurança da camada de transporte

Usando a autenticação baseada em formulários, você pode desenvolver uma página da Web que permita que os usuários sejam autenticados usando seu nome de usuário/senha ou usando o cartão inteligente e o PIN. Este tópico se concentra em como implementar a autenticação de cliente de segurança de camada de transporte com o AD FS 2,0. Para obter mais informações sobre os tipos de autenticação do AD FS 2,0, consulte AD FS 2,0: como alterar o tipo de autenticação local em [https://go.microsoft.com/fwlink/p/?LinkId=313384](https://go.microsoft.com/fwlink/p/?linkid=313384) .

<div>


**Para configurar o AD FS 2,0 para suportar a autenticação de cliente**

1.  Faça logon no computador do AD FS 2,0 usando uma conta de administrador de domínio.

2.  Inicie o Windows Explorer.

3.  Navegue até C: \\ Inetpub \\ ADFS \\ ls

4.  Faça uma cópia de backup do arquivo de web.config existente.

5.  Abra o arquivo de web.config existente usando o bloco de notas.

6.  Na barra de menus, selecione **Editar** e, em seguida, selecione **Localizar**.

7.  Pesquisa **\<localAuthenticationTypes\>** .
    
    Observe que há quatro tipos de autenticação listados, um por linha.

8.  Mova a linha que contém o tipo de autenticação TLSClient para a parte superior da lista na seção.

9.  Salve e feche o arquivo web.config.

10. Inicie um prompt de comando com privilégios elevados.

11. Reinicie o IIS executando o seguinte comando:
    
        IISReset /Restart /NoForce

</div>

</div>

<span> </span>

</div>

</div>

</div>

