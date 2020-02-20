---
title: 'Lync Server 2013: preparando para restaurar o Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing to restore Lync Server
ms:assetid: 857e4e02-908e-433a-96c6-be1795a9cb61
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202179(v=OCS.15)
ms:contentKeyID: 51541490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b397f389de461a04974fe063437caaabd9d4137
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152385"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-to-restore-lync-server-2013"></a>Preparando para restaurar o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-21_

Antes de começar a restauração de servidores e bancos de dados após uma falha, você precisa determinar o seguinte:

  - O que precisa ser restaurado.

  - O hardware, o software, os dados e as ferramentas de que você precisa para a restauração.

<div>

## <a name="determining-what-to-restore"></a>Determinando o quê restaurar

Este tópico descreve como restaurar as interrupções do Lync Server que ocorrem no nível do servidor, pool ou repositório de gerenciamento central. Se o repositório de gerenciamento central falhar, sua implantação do Lync Server continuará a funcionar, mas não será possível fazer alterações na configuração. Se um servidor Standard Edition ou de Back-End falhar, o pool de usuário para de funcionar. Se qualquer outro servidor falhar, a magnitude da falha depende da função de servidor que o servidor está executando e de se o servidor hospeda um ou mais bancos de dados.

### <a name="what-to-restore"></a>O que restaurar

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Se isto falhou</th>
<th>Consulte esta seção:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Servidor Standard Edition</p></td>
<td><p><a href="lync-server-2013-restoring-a-standard-edition-server.md">Restaurando um servidor Standard Edition no Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Repositório de Gerenciamento Central</p></td>
<td><p><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">Restaurando o servidor que hospeda o repositório de gerenciamento central no Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Back-end do Enterprise Edition</p></td>
<td><p><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restaurando um servidor back-end Enterprise Edition no Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Servidor primário de back-end do Enterprise Edition espelhado</p></td>
<td><p><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Restaurando um servidor back-end Enterprise Edition espelhado no Lync Server 2013-principal</a></p></td>
</tr>
<tr class="odd">
<td><p>Servidor secundário de back-end do Enterprise Edition espelhado</p></td>
<td><p><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restaurando um servidor back-end Enterprise Edition espelhado no Lync Server 2013-espelho</a></p></td>
</tr>
<tr class="even">
<td><p>Qualquer servidor Enterprise Edition executando uma função de servidor, como um servidor front-end, servidor de borda, diretor, servidor de mediação, ou servidor de chat persistente.</p></td>
<td><p><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restaurando um servidor membro Enterprise Edition no Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Um pool completo do Lync Server</p></td>
<td><p><a href="lync-server-2013-restoring-a-lync-server-pool.md">Restaurando um pool do Lync Server no Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Repositório de arquivos Enterprise Edition</p></td>
<td><p><a href="lync-server-2013-restoring-a-file-store.md">Restaurando um repositório de arquivos no Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Um banco de dados de monitoramento autônomo ou banco de dados de arquivamento</p></td>
<td><p><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">Restauração de dados de monitoramento ou arquivamento no Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Um banco de dados persistente de chat autônomo</p></td>
<td><p><a href="lync-server-2013-restoring-persistent-chat-data.md">Restaurando dados de chat persistente no Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="gathering-hardware-software-and-tools"></a>Coletando hardware, software e ferramentas

Quando você restaurar um servidor, será necessário iniciar com um computador novo ou limpo. Além disso, você deve ter os seguintes hardwares e softwares disponíveis:

  - Um servidor novo ou limpo com o mesmoFQDN (nome de domínio totalmente qualificado) do servidor que falhou.
    
    <div>
    

    > [!IMPORTANT]  
    > Ao instalar o sistema operacional, certifique-se de não excluir a conta de computador nos serviços de domínio do Active Directory e se as permissões de grupo da conta são mantidas.

    
    </div>

  - Software de instalação para o sistema operacional. Para instalar o sistema operacional, use as configurações de implantação do servidor e procedimentos estabelecidos pela organização. Você deve ter esses procedimentos e requisitos de configuração disponíveis ao restaurar o serviço.

  - Software de instalação do SQL Server 2012 ou SQL Server 2008 R2. Para instalar um servidor de banco de dados, use a versão adequada do SQL Server e os procedimentos de implantação do servidor de banco de dados e configurações estabelecidos pela sua organização. Você deve ter esses procedimentos e requisitos de configuração disponíveis ao restaurar o serviço.
    
    <div>
    

    > [!NOTE]  
    > O assistente de implantação do Lync Server instala automaticamente o SQL Server 2012 Express em cada servidor Standard Edition e em qualquer outro servidor do Lync Server quando um repositório de configuração local é instalado, a menos que você tenha pré-instalado o SQL Server 2012 ou o SQL Server 2008 R2 no o servidor.

    
    </div>

  - Software para fazer imagens de sistema.
    
    <div>
    

    > [!TIP]  
    > Recomendamos que você faça uma cópia de imagem do sistema depois de instalar o sistema operacional e o SQL Server e antes de iniciar a restauração, para que você possa usá-la como um ponto de reversão caso algo dê errado durante a restauração.

    
    </div>

  - Software de instalação do Lync Server 2013. O assistente de implantação do Lync Server está localizado na pasta de instalação do Lync Server \\ou\\na\\mídia no arquivo de instalação amd64. exe.

Durante a restauração, você pode usar as seguintes ferramentas:

  - Cmdlets do Shell de gerenciamento do Lync Server

  - Import-CsUserData

  - Ferramentas para restaurar as pastas do Windows

  - Construtor de Topologias

  - Utilitários de banco de dados de SQL Server, como o SQL Server Management Studio

</div>

<div>

## <a name="preparing-to-restore-a-server"></a>Preparação para restaurar um servidor

Antes de restaurar o servidor, você deve executar as seguintes etapas:

1.  Instale o sistema operacional.

2.  Se o servidor for um servidor back-end, instale o SQL Server 2012 ou o SQL Server 2008 R2.

3.  Restaure ou registre novamente os certificados. Para obter detalhes sobre certificados, consulte "requisitos adicionais de backup" em [requisitos de backup e restauração no Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md).

4.  Tire uma imagem do sistema antes de iniciar a restauração para usar como um ponto de reversão, caso algo dê errado durante a restauração.

<div>


> [!NOTE]  
> O assistente de implantação do Lync Server e os cmdlets descritos nos procedimentos deste tópico e tópicos relacionados, define todas as listas de controle de acesso (ACLs) necessárias.



</div>

Verifique se o hardware e o software necessários para os componentes que você planeja restaurar estão disponíveis antes de iniciar a restauração. Depois de instalar o sistema operacional e o SQL Server, a maioria das etapas nos procedimentos de restauração a seguir pode ser executada remotamente. As exceções estão indicadas nos procedimentos.

Você também deve ter o plano de backup e restauração da sua organização e as informações do seu último backup, como as informações nas planilhas deste documento (para obter detalhes, consulte [planilhas de backup e restauração para o Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)), disponível antes de iniciar a restauração.

</div>

</div>

<span> </span>

</div>

</div>

</div>

