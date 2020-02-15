---
title: 'Lync Server 2013: testar o servidor Standard Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the Standard Edition server
ms:assetid: b6ef67bb-9665-43e4-b8b3-eac8898eebf6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412890(v=OCS.15)
ms:contentKeyID: 48185220
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4145740f09557c8f39830dce689fa122456a28f8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018972"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-the-standard-edition-server-in-lync-server-2013"></a>Testar o servidor Standard Edition no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-01_

O procedimento a seguir descreve como testar a implantação de um servidor Standard Edition.

<div>

## <a name="to-test-the-deployment-of-a-standard-edition-server"></a>Para testar a implantação de um servidor Standard Edition

1.  Use usuários e computadores do Active Directory para adicionar o objeto de usuário do Active Directory da função de administrador para a implantação do Lync Server 2013 (em que o painel de controle do Lync Server está instalado) no grupo **CSAdministrator** .

2.  Se o objeto de usuário estiver conectado no momento, saia e faça logon novamente para registrar a nova atribuição de grupo.
    
    <div>
    

    > [!NOTE]  
    > A conta de usuário não pode ser o administrador local do servidor que executa o Lync Server 2013, Standard Edition. Se você não adicionar os usuários e grupos apropriados ao grupo CsAdministors, receberá um erro ao abrir o painel de controle do Lync Server 2013, que afirma que "não autorizado: acesso negado devido a uma falha de autorização de controle de acesso baseado em função (RBAC)."

    
    </div>

3.  Use a conta administrativa para fazer logon no computador onde o painel de controle do Lync Server está instalado.

4.  Inicie o painel de controle do Lync Server e forneça as credenciais, se solicitado. O painel de controle do Lync Server 2013 exibe informações de implantação.

5.  Na barra de navegação esquerda, clique em **topologia**e confirme se o status do serviço é um ícone de computador com uma seta verde e se há uma marca de seleção verde ao lado de cada função de servidor do Lync Server que foi implantada e colocada online.

6.  Na barra de navegação esquerda, clique em **usuários**e habilite os dois usuários do Lync Server 2013.

7.  Faça logon de um usuário no computador que ingressou no domínio e do outro usuário em outro computador no domínio.

8.  Instale o Lync Server 2013 em cada um dos dois computadores cliente e verifique se ambos os usuários podem entrar no Lync Server 2013 e enviar mensagens instantâneas entre si.

</div>

<div>

## <a name="see-also"></a>Confira também


[Implantando clientes e dispositivos no Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

