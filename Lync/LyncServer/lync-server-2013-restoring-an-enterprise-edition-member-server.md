---
title: 'Lync Server 2013: restaurar um servidor membro Enterprise Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring an Enterprise Edition member server
ms:assetid: d960b19c-2104-4719-b736-0d940f254d42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202191(v=OCS.15)
ms:contentKeyID: 51541523
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c0643cf250e00b447bfac8a1b32c2a3038cff139
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051083"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-an-enterprise-edition-member-server-in-lync-server-2013"></a>Restaurando um servidor membro Enterprise Edition no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-18_

Se um servidor que executa uma das seguintes funções de servidor falhar, siga o procedimento neste tópico para restaurar o servidor. Se vários servidores falharem independentemente, siga o procedimento para cada servidor.

  - Servidor Front-End

  - Servidor de Mediação

  - Be

  - Servidor de chat persistente

  - Servidor de Borda

<div>


> [!TIP]  
> Recomendamos que você faça uma cópia de imagem do sistema antes de iniciar a restauração. Você pode usar essa imagem como um ponto de reversão, caso algo dê errado durante a restauração. Você pode querer fazer a cópia da imagem depois de instalar o sistema operacional e o SQL Server e restaurar ou registrar novamente os certificados.



</div>

<div>

## <a name="to-restore-a-member-server"></a>Para restaurar um servidor membro

1.  Comece com um servidor limpo ou novo que tenha o mesmo FQDN (nome de domínio totalmente qualificado) que o servidor com falha, instale o sistema operacional e restaure ou registre novamente os certificados.
    
    <div>
    

    > [!NOTE]  
    > Siga os procedimentos de implantação de servidor de sua organização para executar essa etapa.

    
    </div>

2.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins, faça logon no servidor que você está restaurando.

3.  Navegue até a pasta ou a mídia de instalação do Lync Server e inicie o assistente de implantação do \\Lync\\Server\\localizado em setup AMD64. exe.

4.  Siga o Assistente de Implantação para executar o seguinte:
    
    1.  Execute **Etapa 1: Instalar Repositório de Configuração Local** para instalar os arquivos de configuração locais.
    
    2.  Execute **etapa 2: instalar ou remover componentes do Lync Server** para instalar a função de servidor do Lync Server.
    
    3.  Execute **Etapa 3: Solicitar, Instalar ou Ceder Certificados** para atribuir os certificados.
    
    4.  Execute **Etapa 4: Iniciar os Serviços** para iniciar os serviços no servidor.
    
    Para obter detalhes sobre como executar o assistente de implantação, consulte a documentação de implantação para a função de servidor que você está restaurando.

</div>

</div>

<span> </span>

</div>

</div>

</div>

