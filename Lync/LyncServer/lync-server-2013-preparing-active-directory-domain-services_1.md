---
title: 'Lync Server 2013: preparando serviços de domínio do Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing Active Directory Domain Services
ms:assetid: 7b0d9aa4-f1ab-4578-b22f-b802b6ed1530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398607(v=OCS.15)
ms:contentKeyID: 48184583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7c5d83acbe32d33a235e7c2918663340a3ac7ce
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183751"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-active-directory-domain-services-in-lync-server-2013"></a>Preparando os serviços de domínio do Active Directory no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-02-19_

No Lync Server 2013, você pode usar o assistente de implantação do Lync Server para preparar os serviços de domínio do Active Directory, ou você pode usar os cmdlets do Shell de gerenciamento do Lync Server diretamente. Também pode usar a ferramenta de linha de comando ldifde.exe diretamente nos seus controladores de domínio, conforme descrito mais adiante neste tópico.

O assistente de implantação do Lync Server orienta você por meio de cada tarefa de preparação do Active Directory. O assistente de implantação executa os cmdlets do Shell de gerenciamento do Lync Server. Essa ferramenta é útil para ambientes com um único domínio e topologia de floresta, ou outra topologia semelhante.

<div>


> [!IMPORTANT]  
> Você pode implantar o Lync Server em uma floresta ou domínio em que os controladores de domínio executam versões de 32 bits de alguns sistemas operacionais (para obter detalhes, consulte <A href="lync-server-2013-active-directory-infrastructure-requirements.md">Active Directory Infrastructure Requirements for Lync Server 2013</A>). No entanto, não é possível usar o assistente de implantação do Lync Server para executar o esquema, a floresta e a preparação do domínio nesses ambientes, pois o assistente de implantação e os arquivos de suporte são 64 bits. Em vez disso, você pode usar o Ldifde.exe e os arquivos .ldf associados em um controlador de domínio de 32 bits para preparar o esquema, a floresta e domínio. Consulte a seção "Usando os Cmdlets e Ldifde.exe" posteriormente neste tópico.



</div>

Você pode usar os cmdlets do Shell de gerenciamento do Lync Server para executar tarefas remotamente ou para ambientes mais complexos.

<div>

## <a name="active-directory-preparation-prerequisites"></a>Pré-requisitos de preparação do Active Directory

Você deve executar as etapas de preparação do Active Directory em um computador que executa o Windows Server 2012, o Windows Server 2012 R2 ou o Windows Server 2008 R2 com SP1 (64 bits). A preparação do Active Directory requer o Shell de gerenciamento do Lync Server e o OCSCore.

Os seguintes componentes são necessários para executar tarefas de preparação do Active Directory:

  - Componentes principais do Lync Server (OCScore. msi)
    
    <div>
    

    > [!NOTE]  
    > Se você planeja usar o Shell de gerenciamento do Lync Server para a preparação do Active Directory, você deve executar o assistente de implantação do Lync Server primeiro para instalar os componentes principais.

    
    </div>

  - Microsoft .NET Framework 4.5
    
    <div>
    

    > [!NOTE]  
    > Para o Windows Server 2012 e o Windows Server 2012 R2, você instala e ativa o .NET Framework 4,5 usando o Gerenciador do servidor. Para obter detalhes, consulte "Microsoft .NET Framework 4,5" em <A href="lync-server-2013-additional-software-requirements.md">Additional Software Requirements for Lync Server 2013</A>. Para o Windows&nbsp;Server&nbsp;2008 R2, baixe e instale o <A href="https://www.microsoft.com/download/details.aspx?id=30653">.NET Framework 4,5</A> no site da Microsoft.

    
    </div>

  - Ferramentas de administração de servidor remoto (RSAT)
    
    <div>
    

    > [!NOTE]  
    > Algumas ferramentas RSAT são necessárias se você for executar as etapas de preparação do Active Directory em um servidor membro em vez de em um controlador de domínio. Instale as ferramentas de linha de comando e snap-ins do AD DS e o módulo do Active Directory para Windows PowerShell a partir do nó do AD DS e das ferramentas do AD LDS no Gerenciador do servidor.

    
    </div>

  - Microsoft Visual C++ 11 Redistributable
    
    <div>
    

    > [!NOTE]  
    > O programa de instalação solicita que você instale esse pré-requisito, se ele já não estiver instalado no computador. O pacote é fornecido para você e não terá que adquirí-lo separadamente.

    
    </div>

  - Windows PowerShell 3,0 (64 bits)
    
    Para o Windows Server 2012 e o Windows Server 2012 R2, o Windows PowerShell 3,0 deve ser incluído na sua instalação do Lync Server 2013. Para o Windows Server 2008 R2, você precisa instalar ou atualizar para o Windows PowerShell 3,0. Para obter detalhes, consulte [instalando o Windows PowerShell 3,0 para Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md)

</div>

<div>

## <a name="administrator-rights-and-roles"></a>Funções e direitos do administrador

A tabela a seguir mostra as funções e os direitos administrativos necessários para cada tarefa de preparação do Active Directory.

### <a name="user-rights-required-for-active-directory-preparation"></a>Direitos de usuário necessários para a preparação do Active Directory

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Procedimento</th>
<th>Direitos ou funções</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Preparação do esquema</p></td>
<td><p>Membro do grupo Administradores de esquema para o domínio raiz da floresta e os direitos do administrador no mestre de esquema</p></td>
</tr>
<tr class="even">
<td><p>Preparação da floresta</p></td>
<td><p>Membro do grupo Administradores de empresa para a floresta</p></td>
</tr>
<tr class="odd">
<td><p>Preparação do domínio</p></td>
<td><p>Membro do grupo Administradores de empresa ou Administradores do domínio para o domínio especificado</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="active-directory-preparation-cmdlets"></a>Cmdlets de preparação do Active Directory

A tabela a seguir compara os cmdlets do Shell de gerenciamento do Lync Server usados para preparar o AD DS para os comandos do LcsCmd usados para preparar o AD DS no Microsoft Office Communications Server 2007 R2.

### <a name="cmdlets-compared-to-lcscmd"></a>Cmdlets comparados a LcsCmd

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Cmdlets</th>
<th>LcsCmd</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Install-CsAdServerSchema</p></td>
<td><p>Lcscmd /forest /action:SchemaPrep /SchemaType:Server</p></td>
</tr>
<tr class="even">
<td><p>Get-CsAdServerSchema</p></td>
<td><p>Lcscmd /forest /action:CheckSchemaPrepState</p></td>
</tr>
<tr class="odd">
<td><p>Enable-CsAdForest</p></td>
<td><p>Lcscmd /forest /action:ForestPrep</p></td>
</tr>
<tr class="even">
<td><p>Disable-CsAdForest</p></td>
<td><p>Lcscmd /forest /action:ForestUnprep</p></td>
</tr>
<tr class="odd">
<td><p>Get-CsAdForest</p></td>
<td><p>Lcscmd /forest /action:CheckForestPrepState</p></td>
</tr>
<tr class="even">
<td><p>Enable-CsAdDomain</p></td>
<td><p>Lcscmd /domain /action:DomainPrep</p></td>
</tr>
<tr class="odd">
<td><p>Disable-CsAdDomain</p></td>
<td><p>Lcscmd /domain /action: DomainUnprep</p></td>
</tr>
<tr class="even">
<td><p>Get-CsAdDomain</p></td>
<td><p>Lcscmd /domain /action:CheckDomainPrepState</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="locked-down-active-directory-requirements"></a>Requisitos do Active Directory bloqueado

Se a herança das permissões estiver desabilitada ou as permissões de usuário autenticadas tiverem que ser desabilitadas na organização, execute etapas adicionais durante a preparação do domínio. Para obter detalhes, consulte [preparação de serviços de domínio do Active Directory bloqueados no Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).

</div>

<div>

## <a name="custom-container-permissions"></a>Permissões de contêiner personalizadas

Se sua organização usa contêineres personalizados em vez de três contêineres internos  (controladores de usuários, computadores e domínio), você deve conceder o acesso de leitura aos contêineres personalizados para o grupo Usuários autenticados. O acesso de leitura aos contêineres é necessário para a preparação do domínio. Para obter detalhes, consulte [preparando domínios para o Lync Server 2013](lync-server-2013-preparing-domains.md).

</div>

<div>

## <a name="using-cmdlets-and-ldifdeexe"></a>Usando Cmdlets e Ldifde.exe

A etapa **preparar esquema** no assistente de implantação do Lync Server e o cmdlet **install-CsAdServerSchema** estender o esquema do Active Directory em controladores de domínio que executam um sistema operacional de 64 bits. Se você precisa estender o esquema do Active Directory em um controlador de domínio executando um sistema operacional de 32 bits, execute o cmdlet **Install-CsAdServerSchema** remotamente a partir de um servidor membro (abordagem recomendada). No entanto, se for necessário executar a preparação do esquema diretamente no controlador de domínio, você pode usar a ferramenta Ldifde.exe para importar os arquivos de esquema. A ferramenta Ldifde.exe é fornecida com a maioria das versões do sistema operacional Windows.

Se você usar o Ldifde.exe para importar os arquivos de esquema, importe todos os quatro arquivos independentemente de estar migrando de uma versão anterior ou executando uma instalação limpa. Você deve importá-los na seguinte seqüência:

1.  ExternalSchema. ldf

2.  ServerSchema. ldf

3.  BackCompatSchema. ldf

4.  VersionSchema. ldf

<div>


> [!NOTE]  
> Os quatro arquivos .ldf estão localizados em \Suporte\ diretório de esquema na mídia de instalação ou download.



</div>

Para usar o Ldifde.exe na importação dos arquivos de quatro esquemas em um controlador de domínio que é o mestre de esquema, use o seguinte formato:

    ldifde -i -v -k -s <DCName> -f <Schema filename> -c DC=X <defaultNamingContext> -j logFilePath -b <administrator account> <logon domain> <password>

Por exemplo:

    ldifde -i -v -k -s DC1 -f ServerSchema.ldf -c DC=X "DC=contoso,DC=com" -j C:\BatchImportLogFile -b Administrator contoso password

<div>


> [!NOTE]  
> Use o parâmetro b somente se estiver conectado como um usuário diferente. Para obter detalhes sobre os direitos necessários, consulte a seção "Direitos e funções do administrador" anteriormente neste tópico.



</div>

Para usar o Ldifde.exe na importação dos arquivos de quatro esquemas em um controlador de domínio que não é o mestre de esquema, use o seguinte formato:

    ldifde -i -v -k -s <SchemaMasterFQDN> -f <Schema filename> -c DC=X <rootDomainNamingContext> -j logFilePath -b <administrator account> <domain> <password>

Para obter detalhes sobre como usar o Ldifde, consulte o artigo 237677 da base de dados de conhecimento da Microsoft, "usando o LDIFDE para importar [https://go.microsoft.com/fwlink/p/?linkId=132204](https://go.microsoft.com/fwlink/p/?linkid=132204)e exportar objetos de diretório para o Active Directory" em.

</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Preparando o esquema do Active Directory no Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)

  - [Preparando a floresta para o Lync Server 2013](lync-server-2013-preparing-the-forest.md)

  - [Preparando domínios para o Lync Server 2013](lync-server-2013-preparing-domains.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

