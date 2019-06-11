---
title: 'Lync Server 2013: restaurando um servidor membro da Enterprise Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring an Enterprise Edition member server
ms:assetid: d960b19c-2104-4719-b736-0d940f254d42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202191(v=OCS.15)
ms:contentKeyID: 51541523
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83f0283dc6525dbb75ce74809bd88f4e962a9aec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822969"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-an-enterprise-edition-member-server-in-lync-server-2013"></a>Restaurando um servidor membro da Enterprise Edition no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-18_

Se um servidor com uma das funções a seguir falhar, siga o procedimento deste tópico para restaurar o servidor. Se vários servidores falharem independentemente, siga o procedimento para cada servidor.

  - Servidor Front-End

  - Servidor de Mediação

  - Diretor

  - Servidor de Chat Persistente

  - Servidor de Borda

<div>


> [!TIP]  
> Recomendamos que você tire uma cópia da imagem do sistema antes de iniciar a restauração. Você pode usar essa imagem como um ponto de recuperação, caso algo dê errado durante a restauração. Talvez você queira fazer a cópia da imagem depois de instalar o sistema operacional e o SQL Server, e restaurar ou registrar novamente os certificados.



</div>

<div>

## <a name="to-restore-a-member-server"></a>Para restaurar um servidor membro

1.  Comece com um servidor limpo ou novo que tenha o mesmo FQDN (nome de domínio totalmente qualificado) da mesma forma que o servidor com falha, instale o sistema operacional e, em seguida, restaure ou registre novamente os certificados.
    
    <div>
    

    > [!NOTE]  
    > Siga os procedimentos de implantação do servidor da sua organização para executar esta etapa.

    
    </div>

2.  Em uma conta de usuário que seja um membro do grupo RTCUniversalServerAdmins, faça logon no servidor que você está restaurando.

3.  Navegue até a pasta de instalação ou a mídia do Lync Server e inicie o assistente de implantação do \\Lync\\Server\\localizado em setup AMD64 setup. exe.

4.  Siga o assistente de implantação para fazer o seguinte:
    
    1.  Execute a **etapa 1: instalar o repositório de configuração local** para instalar os arquivos de configuração local.
    
    2.  Execute a **etapa 2: configurar ou remover componentes do Lync Server** para instalar a função do servidor do Lync Server.
    
    3.  Execute a **etapa 3: solicitar, instalar ou atribuir certificados** para atribuir os certificados.
    
    4.  Execute a **etapa 4: Iniciar serviços** para iniciar serviços no servidor.
    
    Para obter detalhes sobre como executar o assistente de implantação, consulte a documentação de implantação para a função de servidor que você está restaurando.

</div>

</div>

<span> </span>

</div>

</div>

</div>

