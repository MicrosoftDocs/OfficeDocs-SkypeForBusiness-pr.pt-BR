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
ms.openlocfilehash: c48e474c511fd8d2e4b3e84bea0d74fcfeb650ac
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191954"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-ad-fs-20-to-support-client-authentication-in-lync-server-2013"></a>Configurando o AD FS 2,0 para suportar a autenticação de cliente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-07-03_

Há dois tipos de autenticação possíveis que podem ser configurados para permitir que o AD FS 2,0 suporte a autenticação usando cartões inteligentes:

  - Autenticação baseada em formulários (FBA)

  - Autenticação do cliente de segurança da camada de transporte

Usando a autenticação baseada em formulários, você pode desenvolver uma página da Web que permita que os usuários sejam autenticados usando seu nome de usuário/senha ou usando o cartão inteligente e o PIN. Este tópico se concentra em como implementar a autenticação de cliente de segurança de camada de transporte com o AD FS 2,0. Para obter mais informações sobre os tipos de autenticação do AD FS 2,0, consulte AD FS 2,0: como alterar o tipo [https://go.microsoft.com/fwlink/p/?LinkId=313384](https://go.microsoft.com/fwlink/p/?linkid=313384)de autenticação local em.

<div>


**Para configurar o AD FS 2,0 para suportar a autenticação de cliente**

1.  Faça logon no computador do AD FS 2,0 usando uma conta de administrador de domínio.

2.  Inicie o Windows Explorer.

3.  Navegue até C:\\Inetpub\\ADFS\\ls

4.  Faça uma cópia de backup do arquivo Web. config existente.

5.  Abra o arquivo Web. config existente usando o bloco de notas.

6.  Na barra de menus, selecione **Editar** e, em seguida, selecione **Localizar**.

7.  Procure ** \<localAuthenticationTypes\>**.
    
    Observe que há quatro tipos de autenticação listados, um por linha.

8.  Mova a linha que contém o tipo de autenticação TLSClient para a parte superior da lista na seção.

9.  Salve e feche o arquivo Web. config.

10. Inicie um prompt de comando com privilégios elevados.

11. Reinicie o IIS executando o seguinte comando:
    
        IISReset /Restart /NoForce

</div>

</div>

<span> </span>

</div>

</div>

</div>

