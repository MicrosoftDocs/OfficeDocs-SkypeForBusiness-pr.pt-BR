---
title: 'Lync Server 2013: instalar o banco de dados do servidor Standard Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Standard Edition server database
ms:assetid: 0bd3a804-aad6-48cb-981b-54725af032db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398167(v=OCS.15)
ms:contentKeyID: 48183385
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0386caebab3b50854ae608d947b6cd674922c155
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135688"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-standard-edition-server-database-for-lync-server-2013"></a>Instalar o banco de dados do servidor Standard Edition para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-01_

Configurar um servidor Standard Edition como o único servidor em sua infraestrutura que os usuários diferem de outras instalações de servidor, pois há uma seleção no **Assistente de implantação** especificamente para configurar o servidor inicial.

<div>

## <a name="to-install-a-standard-edition-server"></a>Para instalar um servidor do Standard Edition

1.  Faça logon no servidor no qual você instalará o servidor Standard Edition como um administrador local ou um domínio equivalente.

2.  Se você não tiver preparado os serviços de domínio do Active Directory, primeiro execute esses procedimentos. Para obter detalhes, consulte [preparando os serviços de domínio do Active Directory para o Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).

3.  No assistente de implantação do Lync Server, clique em **preparar primeiro servidor Standard Edition**.

4.  Na página **Preparar primeiro servidor Standard Edition**, clique em **Avançar**.

5.  Na página **executando comandos** , o SQL Server 2012 Express é instalado como o repositório de gerenciamento central. Regras de firewall necessárias são criadas. Quando a instalação do banco de dados e software de pré-requisito estiver concluída, clique em **Finalizar**.
    
    <div>
    

    > [!NOTE]  
    > A instalação inicial pode levar algum tempo sem nenhuma atualização visível na tela de resumo de saída do comando. Isso ocorre devido à instalação do SQL Server Express. Se você precisa monitorar a instalação do banco de dados, use o Gerenciador de Tarefas para monitorar a configuração.

    
    </div>

6.  Na página Assistente de implantação do Lync Server, clique em **instalar Construtor de topologia** se você ainda não tiver instalado as ferramentas administrativas. Para obter detalhes, consulte [install Lync Server 2013 Administrative Tools](lync-server-2013-install-lync-server-administrative-tools.md).

7.  Confirme se há marcas de seleção verdes ao lado de “Preparar Active Directory,” “Preparar primeiro servidor Standard Edition” e “Instalar Construtor de Topologias”.

</div>

</div>

<span> </span>

</div>

</div>

</div>

