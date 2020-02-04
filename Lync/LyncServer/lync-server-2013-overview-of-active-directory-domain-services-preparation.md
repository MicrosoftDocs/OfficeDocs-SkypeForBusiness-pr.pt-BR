---
title: 'Lync Server 2013: Visão geral da preparação do Serviços de Domínio Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Active Directory Domain Services preparation
ms:assetid: cdd2a652-6a0d-4728-9950-3fcaa7a80066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398869(v=OCS.15)
ms:contentKeyID: 48185662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d51d0fec8f36749f52acf3272bf83dee3170da8f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755625"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-active-directory-domain-services-preparation-in-lync-server-2013"></a>Visão geral da preparação do Serviços de Domínio Active Directory no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-29_

Para preparar os serviços de domínio do Active Directory para a implantação do Lync Server 2013, você deve executar três etapas em uma sequência específica.

A tabela a seguir descreve as etapas necessárias para preparar o AD DS para o Lync Server.

### <a name="active-directory-preparation-steps"></a>Etapas de preparação do Active Directory

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Etapa</th>
<th>Descrição</th>
<th>Onde executar</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1.</p></td>
<td><p><a href="lync-server-2013-preparing-the-active-directory-schema.md">Preparando o esquema do Active Directory no Lync Server 2013</a></p></td>
<td><p>Estende o esquema do Active Directory adicionando novas classes e atributos que são usados pelo Lync Server.</p>
<p>Executar uma vez para cada floresta na sua implantação em que o Lync Server será implantado.</p></td>
<td><p>Em relação ao mestre de esquema no domínio raiz de cada floresta em que o Lync Server será implantado.</p>
<div>

> [!NOTE]  
> Você não precisará executar esta etapa no domínio raiz se tiver permissões no mestre de esquema, mas você deve ser um membro do grupo de administradores de esquemas no domínio raiz e um membro do grupo Administradores de empresa no mestre de esquema. Em uma topologia de floresta de recursos, execute esta etapa somente na floresta de recursos, não em nenhuma floresta de usuário. Em uma topologia de floresta central, execute esta etapa somente na floresta central, e não em qualquer floresta de usuário.


</div></td>
</tr>
<tr class="even">
<td><p>2.</p></td>
<td><p><a href="lync-server-2013-preparing-the-forest.md">Preparando a floresta para Lync Server 2013</a></p></td>
<td><p>Cria configurações globais e grupos universais usados pelo Lync Server.</p>
<p>Executar uma vez para cada floresta na sua implantação em que o Lync Server será implantado.</p></td>
<td><p>No domínio raiz de cada floresta em que o Lync Server será implantado. Para executar esta etapa, você deve ser membro do grupo Administradores da empresa.</p>
<div>

> [!NOTE]  
> Em uma topologia de floresta de recursos, execute esta etapa somente na floresta de recursos, não em nenhuma floresta de usuário. Em uma topologia de floresta central, execute esta etapa somente na floresta central, e não em qualquer floresta de usuário.


</div></td>
</tr>
<tr class="odd">
<td><p>3.</p></td>
<td><p><a href="lync-server-2013-preparing-domains.md">Preparando domínios para Server 2013</a></p></td>
<td><p>Adiciona permissões em objetos a serem usadas por membros de grupos universais.</p>
<p>Executar uma vez por domínio do usuário ou domínio do servidor.</p>
<div>

> [!NOTE]  
> Se você estiver migrando do Lync Server 2010 para o Lync Server 2013, o assistente de implantação poderá indicar que a preparação do domínio já está concluída. Você não precisa executar a preparação do domínio novamente. As permissões não foram alteradas do Lync Server 2010 para o Lync Server 2013.


</div></td>
<td><p>Em um servidor membro em cada domínio em que o Lync Server será implantado. Para executar esta etapa, você deve ser membro do grupo Domain admins.</p></td>
</tr>
</tbody>
</table>


<div id="sectionSection0" class="section">

O Lync Server 2013, como o Lync Server 2010, armazena muitas das informações de configuração no repositório de gerenciamento central em vez de no AD DS como era o caso no Office Communications Server 2007 R2. No entanto, as seguintes informações são armazenadas no AD DS:

  - **Extensões de esquema**:
    
      - Extensões de objetos de usuário
    
      - Extensões para as classes do Office Communications Server 2007 R2 para manter a compatibilidade com versões anteriores

<!-- end list -->

  - **Dados** (armazenados no esquema estendido do Lync Server e em classes de esquema existentes):
    
      - URI (Uniform Resource Identifier) do usuário SIP e outras configurações do usuário
    
      - Objetos de contato para aplicativos como o assistente de grupo de resposta e conferência
    
      - Um ponteiro para o repositório de gerenciamento central
    
      - Conta de autenticação Kerberos (um objeto de computador opcional)

No Lync Server 2013, você delega a instalação e a administração concedendo permissões de instalação ao grupo universal RTCUniversalServerAdmins para que os membros desse grupo possam instalar e ativar o Lync Server 2013 em um servidor local (após a adição do servidor ao topologia, publicada e habilitada). Os usuários delegados devem ser administradores locais no computador em que estão instalando e ativando o Lync Server 2013, mas não precisam ser membros do grupo Domain admins. Você também pode conceder permissões para objetos em unidades organizacionais (UOs) especificadas para que os membros dos grupos universais criados durante a preparação da floresta possam acessar esses objetos sem serem membros do grupo Domain admins.

Para novas implantações do Lync Server 2013, as configurações globais devem ser armazenadas no contêiner de configuração. Se a sua organização estiver atualizando de uma versão anterior e ainda houver configurações globais no contêiner do sistema, o contêiner do sistema ainda tem suporte.

</div>

<div>

## <a name="see-also"></a>Confira também


[Preparando o esquema do Active Directory no Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)  
[Extensões, classes e atributos do esquema do Active Directory usado pelo Lync Server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)  


[Preparando a floresta para Lync Server 2013](lync-server-2013-preparing-the-forest.md)  
[Preparando domínios para Server 2013](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

