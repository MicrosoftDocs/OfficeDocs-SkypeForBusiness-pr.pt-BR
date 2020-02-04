---
title: 'Lync Server 2013: Instalar o banco de dados do servidor Standard Edition'
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
ms.openlocfilehash: 63f2ef304b1a603203d09f260b8d3c7c46e23ccf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763685"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-standard-edition-server-database-for-lync-server-2013"></a>Instalar o banco de dados do servidor Standard Edition para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-01_

Configurar um servidor Standard Edition como o único servidor na sua infraestrutura que os usuários de casas, que diferem de outras instalações de servidor, há uma seleção no **Assistente de implantação** especificamente para configurar o servidor inicial.

<div>

## <a name="to-install-a-standard-edition-server"></a>Para instalar um servidor Standard Edition

1.  Faça logon no servidor no qual você vai instalar o servidor Standard Edition como administrador local ou um equivalente a um domínio.

2.  Se você não tiver preparado os serviços de domínio Active Directory, execute esses procedimentos primeiro. Para obter detalhes, consulte [preparando os serviços de domínio Active Directory para o Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).

3.  No assistente de implantação do Lync Server, clique em **preparar primeiro servidor Standard Edition**.

4.  Na página **preparar único servidor de edição padrão** , clique em **Avançar**.

5.  Na página **comandos em execução** , o SQL Server 2012 Express está instalado como o repositório de gerenciamento central. Regras de firewall necessárias são criadas. Quando a instalação do banco de dados e do software de pré-requisito estiver concluída, clique em **concluir**.
    
    <div>
    

    > [!NOTE]  
    > A instalação inicial pode levar algum tempo sem atualizações visíveis para a tela Resumo da saída do comando. Isso se deve à instalação do SQL Server Express. Se você precisar monitorar a instalação do banco de dados, use o Gerenciador de tarefas para monitorar a configuração.

    
    </div>

6.  Na página do assistente de implantação do Lync Server, clique em **instalar Construtor de topologia** se você não tiver instalado as ferramentas administrativas anteriormente. Para obter detalhes, consulte [instalar as ferramentas administrativas do Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md).

7.  Confirme se há marcas de seleção verdes ao lado de "preparar o Active Directory", "preparar primeiro servidor de edição padrão" e "instalar Construtor de topologia".

</div>

</div>

<span> </span>

</div>

</div>

</div>

