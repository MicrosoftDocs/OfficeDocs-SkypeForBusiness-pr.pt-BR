---
title: 'Lync Server 2013: Preparando Serviços de Domínio do Active Directory'
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
ms.openlocfilehash: 8abab29930e8b09d0642c84f1e02026d4c554637
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747431"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-active-directory-domain-services-in-lync-server-2013"></a>Preparando Serviços de Domínio do Active Directory no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-02-19_

No Lync Server 2013, você pode usar o assistente de implantação do Lync Server para preparar os serviços de domínio do Active Directory, ou você pode usar os cmdlets do Shell de gerenciamento do Lync Server diretamente. Você também pode usar a ferramenta de linha de comando ldifde. exe diretamente nos controladores de domínio, conforme descrito posteriormente neste tópico.

O assistente de implantação do Lync Server orienta você por meio de cada tarefa de preparação do Active Directory. O assistente de implantação executa cmdlets do Shell de gerenciamento do Lync Server. Essa ferramenta é útil para ambientes com um único domínio e topologia de floresta única ou outra topologia semelhante.

<div>


> [!IMPORTANT]  
> Você pode implantar o Lync Server em uma floresta ou domínio em que os controladores de domínio executem versões de 32 bits de alguns sistemas operacionais (para obter detalhes, consulte <A href="lync-server-2013-active-directory-infrastructure-requirements.md">requisitos de infraestrutura do Active Directory para o Lync Server 2013</A>). No entanto, você não pode usar o assistente de implantação do Lync Server para executar o esquema, a floresta e a preparação do domínio nesses ambientes porque o assistente de implantação e os arquivos de suporte são apenas 64 bits. Em vez disso, você pode usar o LDIFDE. exe e os arquivos. ldf associados em um controlador de domínio de 32 bits para preparar o esquema, a floresta e o domínio. Consulte a seção "usando cmdlets e Ldifde. exe" mais adiante neste tópico.



</div>

Você pode usar os cmdlets do Shell de gerenciamento do Lync Server para executar tarefas remotamente ou para ambientes mais complexos.

<div>

## <a name="active-directory-preparation-prerequisites"></a>Pré-requisitos de preparação do Active Directory

Você deve executar as etapas de preparação do Active Directory em um computador que esteja executando o Windows Server 2012, o Windows Server 2012 R2 ou o Windows Server 2008 R2 com SP1 (64 bits). A preparação do Active Directory requer o Shell de gerenciamento do Lync Server e o OCSCore.

Os seguintes componentes são necessários para executar tarefas de preparação do Active Directory:

  - Componentes principais do Lync Server (OCScore. msi)
    
    <div>
    

    > [!NOTE]  
    > Se você pretende usar o Shell de gerenciamento do Lync Server para a preparação do Active Directory, deve executar o assistente de implantação do Lync Server primeiro para instalar os componentes principais.

    
    </div>

  - Microsoft.NET Framework 4.5
    
    <div>
    

    > [!NOTE]  
    > Para o Windows Server 2012 e o Windows Server 2012 R2, instale e ative o .NET Framework 4,5 usando o Gerenciador de servidores. Para obter detalhes, consulte "Microsoft .NET Framework 4,5" em <A href="lync-server-2013-additional-software-requirements.md">requisitos adicionais de software para o Lync Server 2013</A>. Para o Windows&nbsp;Server&nbsp;2008 R2, baixe e instale o <A href="http://www.microsoft.com/en-us/download/details.aspx?id=30653">.NET Framework 4,5</A> do site da Microsoft.

    
    </div>

  - Ferramentas de administração de servidor remoto (RSAT)
    
    <div>
    

    > [!NOTE]  
    > Algumas ferramentas do RSAT são necessárias se você executar etapas de preparação do Active Directory em um servidor membro em vez de em um controlador de domínio. Instale os snap-ins do AD DS e as ferramentas de linha de comando e o módulo do Active Directory para Windows PowerShell do nó AD DS e ferramentas do AD LDS no Gerenciador de servidores.

    
    </div>

  - Microsoft Visual C++ 11 Redistributable
    
    <div>
    

    > [!NOTE]  
    > A instalação solicitará que você instale esse pré-requisito se ele ainda não estiver instalado no computador. O pacote é fornecido para você, e você não precisa adquiri-lo separadamente.

    
    </div>

  - Windows PowerShell 3,0 (64 bits)
    
    Para o Windows Server 2012 e o Windows Server 2012 R2, o Windows PowerShell 3,0 deve estar incluído na instalação do Lync Server 2013. Para o Windows Server 2008 R2, você precisa instalar ou atualizar para o Windows PowerShell 3,0. Para obter detalhes, consulte [instalando o Windows PowerShell 3,0 para Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md)

</div>

<div>

## <a name="administrator-rights-and-roles"></a>Direitos e funções de administrador

A tabela a seguir mostra os direitos administrativos e as funções necessárias para cada tarefa de preparação do Active Directory.

### <a name="user-rights-required-for-active-directory-preparation"></a>Direitos de usuário necessários para a preparação do Active Directory

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Processo</th>
<th>Direitos ou funções</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Preparação do esquema</p></td>
<td><p>Membro do grupo Administradores de esquemas para os direitos de domínio raiz da floresta e administrador no mestre de esquema</p></td>
</tr>
<tr class="even">
<td><p>Preparação da floresta</p></td>
<td><p>Membro do grupo Administradores Corporativos para a floresta</p></td>
</tr>
<tr class="odd">
<td><p>Preparação do domínio</p></td>
<td><p>Membro do grupo administradores corporativos ou administradores de domínio do domínio especificado</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="active-directory-preparation-cmdlets"></a>Cmdlets de preparação do Active Directory

A tabela a seguir compara os cmdlets do Shell de gerenciamento do Lync Server usados para preparar o AD DS para os comandos LcsCmd usados para preparar o AD DS no Microsoft Office Communications Server 2007 R2.

### <a name="cmdlets-compared-to-lcscmd"></a>Cmdlets comparados ao LcsCmd

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
<td><p>LcsCmd/Forest/Action: SchemaPrep/SchemaType: Server</p></td>
</tr>
<tr class="even">
<td><p>Get-CsAdServerSchema</p></td>
<td><p>LcsCmd/Forest/Action: CheckSchemaPrepState</p></td>
</tr>
<tr class="odd">
<td><p>Enable-CsAdForest</p></td>
<td><p>LcsCmd/Forest/Action: ForestPrep</p></td>
</tr>
<tr class="even">
<td><p>Disable-CsAdForest</p></td>
<td><p>LcsCmd/Forest/Action: ForestUnprep</p></td>
</tr>
<tr class="odd">
<td><p>Get-CsAdForest</p></td>
<td><p>LcsCmd/Forest/Action: CheckForestPrepState</p></td>
</tr>
<tr class="even">
<td><p>Enable-CsAdDomain</p></td>
<td><p>LcsCmd/Domain/Action: DomainPrep</p></td>
</tr>
<tr class="odd">
<td><p>Disable-CsAdDomain</p></td>
<td><p>LcsCmd/Domain/Action: DomainUnprep</p></td>
</tr>
<tr class="even">
<td><p>Get-CsAdDomain</p></td>
<td><p>LcsCmd/Domain/Action: CheckDomainPrepState</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="locked-down-active-directory-requirements"></a>Requisitos do Active Directory bloqueados

Se a herança de permissões estiver desabilitada ou as permissões de usuário autenticado tiverem que ser desabilitadas em sua organização, você deverá executar etapas adicionais durante a preparação do domínio. Para obter detalhes, consulte [preparando um serviço de domínio do Active Directory bloqueado no Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).

</div>

<div>

## <a name="custom-container-permissions"></a>Permissões de contêiner personalizado

Se a sua organização usa recipientes personalizados em vez de três contêineres internos (ou seja, usuários, computadores e controladores de domínio), você deve conceder acesso de leitura aos recipientes personalizados para o grupo usuários autenticados. O acesso de leitura aos recipientes é necessário para a preparação do domínio. Para obter detalhes, consulte [preparando domínios para o Lync Server 2013](lync-server-2013-preparing-domains.md).

</div>

<div>

## <a name="using-cmdlets-and-ldifdeexe"></a>Usando cmdlets e Ldifde. exe

A etapa **preparar esquema** no assistente de implantação do Lync Server e o cmdlet **install-CsAdServerSchema** ampliam o esquema do Active Directory em controladores de domínio que executam um sistema operacional de 64 bits. Se você precisar estender o esquema do Active Directory em um controlador de domínio que executa um sistema operacional de 32 bits, poderá executar o cmdlet **install-CsAdServerSchema** remotamente de um servidor membro (abordagem recomendada). No entanto, se você precisar executar a preparação do esquema diretamente no controlador de domínio, poderá usar a ferramenta Ldifde. exe para importar os arquivos de esquema. A ferramenta Ldifde. exe vem com a maioria das versões do sistema operacional Windows.

Se você usar LDIFDE. exe para importar os arquivos de esquema, será necessário importar todos os quatro arquivos, independentemente de você estar migrando de uma versão anterior ou de uma instalação limpa. Você deve importá-las na seguinte sequência:

1.  ExternalSchema. ldf

2.  ServerSchema. ldf

3.  BackCompatSchema. ldf

4.  VersionSchema. ldf

<div>


> [!NOTE]  
> Os quatro arquivos. ldf estão localizados no diretório \Support\Schema da mídia de instalação ou download.



</div>

Para usar o LDIFDE. exe para importar os quatro arquivos de esquema em um controlador de domínio que seja o mestre de esquema, use o seguinte formato:

    ldifde -i -v -k -s <DCName> -f <Schema filename> -c DC=X <defaultNamingContext> -j logFilePath -b <administrator account> <logon domain> <password>

Por exemplo:

    ldifde -i -v -k -s DC1 -f ServerSchema.ldf -c DC=X "DC=contoso,DC=com" -j C:\BatchImportLogFile -b Administrator contoso password

<div>


> [!NOTE]  
> Use o parâmetro b somente se você estiver conectado como um usuário diferente. Para obter detalhes sobre os direitos de usuário necessários, consulte a seção "direitos e funções de administrador" anteriormente neste tópico.



</div>

Para usar o LDIFDE. exe para importar os quatro arquivos de esquema em um controlador de domínio que não seja o mestre de esquema, use o seguinte formato:

    ldifde -i -v -k -s <SchemaMasterFQDN> -f <Schema filename> -c DC=X <rootDomainNamingContext> -j logFilePath -b <administrator account> <domain> <password>

Para obter detalhes sobre como usar o Ldifde, consulte o artigo 237677 da base de dados de conhecimento Microsoft, "usar o LDIFDE para importar e [http://go.microsoft.com/fwlink/p/?linkId=132204](http://go.microsoft.com/fwlink/p/?linkid=132204)exportar objetos de diretório para o Active Directory" em.

</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Preparando o esquema do Active Directory no Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)

  - [Preparando a floresta para Lync Server 2013](lync-server-2013-preparing-the-forest.md)

  - [Preparando domínios para Server 2013](lync-server-2013-preparing-domains.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

