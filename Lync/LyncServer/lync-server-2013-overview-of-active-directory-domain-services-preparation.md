---
title: 'Lync Server 2013: visão geral da preparação dos serviços de domínio do Active Directory'
description: 'Lync Server 2013: visão geral da preparação dos serviços de domínio do Active Directory.'
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
ms.openlocfilehash: 18b22e11a73ad7a181e2eaf887b1b49b934d9db5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566837"
---
# <a name="overview-of-active-directory-domain-services-preparation-in-lync-server-2013"></a>Visão geral da preparação dos serviços de domínio do Active Directory no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-29_

Para preparar os serviços de domínio do Active Directory para a implantação do Lync Server 2013, você deve executar três etapas em uma sequência específica.

A tabela a seguir descreve as etapas necessárias para preparar o AD DS para o Lync Server.

### <a name="active-directory-preparation-steps"></a>Etapas da preparação do Active Directory

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
<p>Executar uma vez para cada floresta em sua implantação onde o Lync Server será implantado.</p></td>
<td><p>No mestre de esquema no domínio raiz de cada floresta onde o Lync Server será implantado.</p>
<div>

> [!NOTE]  
> Não é necessário executar essa etapa no domínio raiz se você tiver permissões no esquema mestre, mas é necessário ser membro do grupo Administradores de Esquema no domínio raiz e membro do grupo Administradores de Empresa no esquema mestre. Em uma topologia de floresta de recursos, execute esta etapa somente na floresta de recursos, e não nas florestas de usuários. Em uma topologia de floresta central, execute esta etapa somente na floresta central, e não nas florestas de usuários.


</div></td>
</tr>
<tr class="even">
<td><p>2.</p></td>
<td><p><a href="lync-server-2013-preparing-the-forest.md">Preparando a floresta para o Lync Server 2013</a></p></td>
<td><p>Cria configurações globais e grupos universais usados pelo Lync Server.</p>
<p>Executar uma vez para cada floresta em sua implantação onde o Lync Server será implantado.</p></td>
<td><p>No domínio raiz de cada floresta onde o Lync Server será implantado. Para executar essa etapa, você precisa ser membro do grupo Administradores de Empresa.</p>
<div>

> [!NOTE]  
> Em uma topologia de floresta de recursos, execute esta etapa somente na floresta de recursos, não em florestas de qualquer usuário. Em uma topologia de floresta central, execute esta etapa somente na floresta central, não em florestas de qualquer usuário.


</div></td>
</tr>
<tr class="odd">
<td><p>3.</p></td>
<td><p><a href="lync-server-2013-preparing-domains.md">Preparando domínios para o Lync Server 2013</a></p></td>
<td><p>Adiciona permissões sobre objetos a serem usados por membros de grupos universais.</p>
<p>Execute uma vez por domínio de usuário ou domínio de servidor.</p>
<div>

> [!NOTE]  
> Se você estiver migrando do Lync Server 2010 para o Lync Server 2013, o assistente de implantação poderá indicar que a preparação do domínio já foi concluída. Não é necessário executar a preparação do domínio novamente. As permissões não foram alteradas do Lync Server 2010 para o Lync Server 2013.


</div></td>
<td><p>Em um servidor membro em cada domínio em que o Lync Server será implantado. Para executar esta etapa, você deve ser membro do grupo Administradores de domínio.</p></td>
</tr>
</tbody>
</table>


<div id="sectionSection0" class="section">

O Lync Server 2013, como o Lync Server 2010, armazena muitas das informações de configuração no repositório de gerenciamento central, em vez de no AD DS, como era o caso no Office Communications Server 2007 R2. No entanto, as seguintes informações são armazenadas no AD DS:

  - **Extensões de esquema**:
    
      - Extensões do objeto do usuário
    
      - Extensões para o Office Communications Server 2007 R2 classes para manter a compatibilidade com versões anteriores

<!-- end list -->

  - **Dados** (armazenados no esquema estendido do Lync Server e nas classes de esquema existentes):
    
      - URI (Uniform Resource Identifier) SIP do usuário e outras configurações de usuário
    
      - Objetos de contato para aplicativos, como Grupo de Respostas e Atendedor de Conferência
    
      - Um ponteiro para o repositório de gerenciamento central
    
      - Conta de autenticação Kerberos (um objeto de computador opcional)

No Lync Server 2013, você delega a instalação e administração, concedendo permissões de configuração ao grupo universal RTCUniversalServerAdmins para que os membros desse grupo possam instalar e ativar o Lync Server 2013 em um servidor local (após o servidor ter sido adicionado à topologia, publicado e habilitado). Os usuários delegados devem ser administradores locais no computador onde estão instalando e ativando o Lync Server 2013, mas não precisam ser membros do grupo de administradores de domínio. Você também pode conceder permissões para objetos em unidades organizacionais (UOs) especificadas, de forma que os membros dos grupos universais criados durante a preparação da floresta possam acessar esses objetos sem ser membros do grupo Administradores de domínio.

Para novas implantações do Lync Server 2013, as configurações globais devem ser armazenadas no contêiner de configuração. Se sua organização estiver atualizando de uma versão anterior e você ainda tiver configurações globais no contêiner do sistema, o contêiner do sistema ainda terá suporte.

</div>

<div>

## <a name="see-also"></a>Confira também


[Preparando o esquema do Active Directory no Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)  
[Extensões, classes e atributos do esquema do Active Directory usados pelo Lync Server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)  


[Preparando a floresta para o Lync Server 2013](lync-server-2013-preparing-the-forest.md)  
[Preparando domínios para o Lync Server 2013](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

