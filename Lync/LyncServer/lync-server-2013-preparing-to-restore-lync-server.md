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
ms.openlocfilehash: c2e6516ee1162c02f2bebc8c385c2f41e87d7781
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724891"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-to-restore-lync-server-2013"></a>Preparando-se para restaurar o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-21_

Antes de começar a restaurar servidores e bancos de dados após uma falha, você precisa determinar o seguinte:

  - O que precisa ser restaurado.

  - O hardware, o software, os dados e as ferramentas necessárias para a restauração.

<div>

## <a name="determining-what-to-restore"></a>Determinar o que restaurar

Este tópico descreve como restaurar as quedas do Lync Server que ocorrem no servidor, no pool ou no nível de repositório de gerenciamento central. Se o repositório de gerenciamento central falhar, a implantação do Lync Server continua a funcionar, mas você não pode fazer alterações de configuração. Se um servidor back-end do servidor ou da edição padrão falhar, o pool de usuários deixará de funcionar. Se qualquer outro servidor falhar, a magnitude da falha dependerá da função do servidor que o servidor está executando e se o servidor hospeda um ou mais bancos de dados.

### <a name="what-to-restore"></a>O que restaurar

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Se isso falhasse</th>
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
<td><p><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restaurando um servidor back-end do Enterprise Edition no Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Servidor primário de back-end do Enterprise Edition</p></td>
<td><p><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Restaurando um servidor back-end da edição Enterprise espelhada no Lync Server 2013-principal</a></p></td>
</tr>
<tr class="odd">
<td><p>Servidor secundário de back-end do Enterprise Edition mirrored</p></td>
<td><p><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restaurando um servidor back-end da edição Enterprise espelhada no Lync Server 2013-Mirror</a></p></td>
</tr>
<tr class="even">
<td><p>Qualquer servidor Enterprise Edition que execute uma função de servidor, como um servidor front-end, servidor de borda, diretor, servidor de mediação ou servidor de chat persistente.</p></td>
<td><p><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restaurando um servidor membro da Enterprise Edition no Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Um pool inteiro do Lync Server</p></td>
<td><p><a href="lync-server-2013-restoring-a-lync-server-pool.md">Restaurando um pool do Lync Server no Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Repositório de arquivos do Enterprise Edition</p></td>
<td><p><a href="lync-server-2013-restoring-a-file-store.md">Restaurando um armazenamento de arquivos no Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Um banco de dados de monitoramento autônomo ou um banco de dados de arquivamento</p></td>
<td><p><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">Restaurando o monitoramento ou arquivando dados no Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Um banco de dados persistente de chat autônomo</p></td>
<td><p><a href="lync-server-2013-restoring-persistent-chat-data.md">Restaurando dados de chat persistente no Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="gathering-hardware-software-and-tools"></a>Reunindo hardware, software e ferramentas

Ao restaurar um servidor, você precisa começar com um computador novo ou limpo. Além disso, você deve ter os seguintes hardware e software disponíveis:

  - Um servidor limpo ou novo com o mesmo FQDN (nome de domínio totalmente qualificado) do servidor que falhou.
    
    <div>
    

    > [!IMPORTANT]  
    > Ao instalar o sistema operacional, certifique-se de não excluir a conta de computador nos serviços de domínio Active Directory e verifique se as permissões de grupo da conta são mantidas.

    
    </div>

  - Software de instalação para o sistema operacional. Para instalar o sistema operacional, use os procedimentos de implantação do servidor e as configurações estabelecidas pela sua organização. Você deve ter esses procedimentos e requisitos de configuração disponíveis quando você restaura o serviço.

  - Software de instalação do SQL Server 2012 ou do SQL Server 2008 R2. Para instalar um servidor de banco de dados, use a versão apropriada do SQL Server e os procedimentos de implantação do servidor de banco de dados e as configurações estabelecidas pela sua organização. Você deve ter esses procedimentos e requisitos de configuração disponíveis quando você restaura o serviço.
    
    <div>
    

    > [!NOTE]  
    > O assistente de implantação do Lync Server instala automaticamente o SQL Server 2012 Express em cada servidor Standard Edition e em qualquer outro servidor do Lync Server quando um repositório de configuração local é instalado, a menos que você tenha pré-instalado o SQL Server 2012 ou o SQL Server 2008 R2 em o servidor.

    
    </div>

  - Software para fazer imagens do sistema.
    
    <div>
    

    > [!TIP]  
    > Recomendamos que você tire uma cópia de imagem do sistema após a instalação do sistema operacional e do SQL Server, e antes de iniciar a restauração, para que você possa usá-la como um ponto de reversão caso algo dê errado durante a restauração.

    
    </div>

  - Software de instalação do Lync Server 2013. O assistente de implantação do Lync Server está localizado na pasta de instalação ou mídia do \\Lync\\Server\\em AMD64 setup. exe.

Durante a restauração, use as seguintes ferramentas:

  - Cmdlets do Shell de gerenciamento do Lync Server

  - Import-CsUserData

  - Ferramentas para restaurar as pastas do Windows

  - Construtor de Topologias

  - Utilitários de banco de dados do SQL Server, como o SQL Server Management Studio

</div>

<div>

## <a name="preparing-to-restore-a-server"></a>Preparando para restaurar um servidor

Antes de restaurar o servidor, você deve executar as seguintes etapas:

1.  Instale o sistema operacional.

2.  Se o servidor for um servidor back-end, instale o SQL Server 2012 ou o SQL Server 2008 R2.

3.  Restaure ou registre novamente seus certificados. Para obter detalhes sobre certificados, consulte "requisitos de backup adicionais" em [requisitos de backup e restauração no Lync Server 2013: dados](lync-server-2013-backup-and-restoration-requirements-data.md).

4.  Tire uma imagem do sistema antes de iniciar a restauração para usar como um ponto de recuperação, caso algo dê errado durante a restauração.

<div>


> [!NOTE]  
> O assistente de implantação do Lync Server e cmdlets descritos nos procedimentos deste tópico e tópicos relacionados, defina todas as listas de controle de acesso (ACLs) necessárias.



</div>

Verifique se o hardware e o software necessários para os componentes que você planeja restaurar estão disponíveis antes de iniciar a restauração. Depois de instalar o sistema operacional e o SQL Server, a maioria das etapas nos seguintes procedimentos de restauração podem ser executadas remotamente. As exceções são observadas nos procedimentos.

Você também deve ter o plano de backup e restauração da sua organização e as informações do último backup, como as informações nas planilhas deste documento (para obter detalhes, consulte [planilhas de backup e restauração do Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)), disponíveis antes de começar a restauração.

</div>

</div>

<span> </span>

</div>

</div>

</div>

