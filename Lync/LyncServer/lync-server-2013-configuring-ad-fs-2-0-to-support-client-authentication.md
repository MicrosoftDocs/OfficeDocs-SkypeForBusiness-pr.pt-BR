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
ms.openlocfilehash: c7fe9587e85ad300a212e4a8199fa4a8a48d1877
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741191"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-ad-fs-20-to-support-client-authentication-in-lync-server-2013"></a>Configurando o AD FS 2,0 para dar suporte à autenticação de cliente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-07-03_

Há dois tipos possíveis de autenticação que podem ser configurados para permitir que o AD FS 2.0 suporte autenticações utilizando cartões inteligentes:

  - Autenticação baseada em formulário (FBA)

  - Autenticação de Cliente de Segurança na Camada de Transporte

Utilizando a autenticação baseada em formulários, você pode desenvolver uma página da Web que permite que os usuários autentiquem usando seus nomes de usuário/senhas ou usando o cartão inteligente e o PIN. Este tópico tem como foco como implementar a Autenticação de Cliente de Segurança na Camada de Transporte com o AD FS 2.0. Para obter mais informações sobre os tipos de autenticação do AD FS 2,0, consulte AD FS 2,0: como alterar o tipo [http://go.microsoft.com/fwlink/p/?LinkId=313384](http://go.microsoft.com/fwlink/p/?linkid=313384)de autenticação local em.

<div>


**Para configurar o AD FS 2.0 para suportar a autenticação de cliente**

1.  Faça logon no computador do AD FS 2.0 utilizando uma conta de Administrador de Domínio.

2.  Inicie o Windows Explorer.

3.  Navegue até C:\\Inetpub\\ADFS\\ls

4.  Faça uma cópia de backup do arquivo web.config existente.

5.  Abra o arquivo web.config existente utilizando o Bloco de Notas.

6.  Na barra de Menu, selecione **Editar** e, em seguida, selecione **Localizar**.

7.  Procure por ** \<localAuthenticationTypes\>**.
    
    Observe que há quatro tipos de autenticação listados, um por linha.

8.  Mova para a linha que contém o tipo de autenticação TLSClient para o topo da lista na seção.

9.  Salve e Feche o arquivo web.config.

10. Inicie um Prompt de Comando com privilégios elevados.

11. Reinicie o IIS executando o seguinte comando:
    
        IISReset /Restart /NoForce

</div>

</div>

<span> </span>

</div>

</div>

</div>

