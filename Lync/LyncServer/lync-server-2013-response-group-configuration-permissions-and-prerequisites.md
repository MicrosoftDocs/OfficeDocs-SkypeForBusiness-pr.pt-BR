---
title: 'Lync Server 2013: Permissões e pré-requisitos de configuração de Grupo de Resposta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response Group configuration permissions and prerequisites
ms:assetid: 4266f16a-b387-452c-a8ca-d771a3c58f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204840(v=OCS.15)
ms:contentKeyID: 48183972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bcf10a61ed5285fe5cfc907c2624a14112d96eae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723631"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-configuration-permissions-and-prerequisites-in-lync-server-2013"></a>Permissões e pré-requisitos de configuração de Grupo de Resposta no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-05_

O grupo de resposta é um recurso de gerenciamento de chamadas de voz corporativa. Este tópico descreve o que você precisa ter em vigor antes de poder configurar o grupo de resposta e as permissões e credenciais administrativas necessárias para executar tarefas de configuração.

Esta seção pressupõe que você leu a documentação de planejamento relacionada ao grupo de resposta. Para obter detalhes, consulte [planejando os recursos de gerenciamento de chamadas no Lync Server 2013](lync-server-2013-planning-for-call-management-features.md) na documentação de planejamento.

<div>

## <a name="configuration-tools-and-administrative-roles"></a>Ferramentas de configuração e funções administrativas

Você pode usar as seguintes ferramentas administrativas para configurar o grupo de resposta:

  - Painel de Controle do Lync Server

  - Ferramenta de Configuração de Grupo de Resposta

  - Shell de Gerenciamento do Lync Server

Para configurar grupos de resposta, você deve ser membro de pelo menos uma das funções administrativas a seguir:


<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Grupo de segurança do Diretório Ativo(1)</strong></p></td>
<td><p>Criar fluxo de trabalho</p></td>
<td><p>Atribuir gerente</p></td>
<td><p>Criar/atribuir agentes, filas</p></td>
<td><p>Criar/gerenciar horas extras e de feriado</p></td>
<td><p>Ativar/Desativar fluxo de trabalho</p></td>
<td><p>Configurar fluxo de trabalho (IVR ou Grupo de busca)</p></td>
</tr>
<tr class="even">
<td><p><strong>CsResponseGroupAdministrator</strong></p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
</tr>
<tr class="odd">
<td><p><strong>CsResponseGroupManager</strong></p></td>
<td> </td>
<td><p>√(2)</p></td>
<td><p>√(3)</p></td>
<td><p>√(3)</p></td>
<td><p>√(3)</p></td>
<td><p>√(3)</p></td>
</tr>
<tr class="even">
<td><p><strong>CsVoiceAdministrator</strong></p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
</tr>
<tr class="odd">
<td><p><strong>CsServerAdministrator</strong></p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
</tr>
<tr class="even">
<td><p><strong>CsAdministrator</strong></p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
</tr>
<tr class="odd">
<td><p><strong>CsViewOnlyAdministrator</strong></p></td>
<td><p>√(4)</p></td>
<td><p>√(4)</p></td>
<td><p>√(4)</p></td>
<td><p>√(4)</p></td>
<td><p>√(4)</p></td>
<td><p>√(4)</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <STRONG>(1)</STRONG> um objeto de usuário dos serviços de domínio Active Directory deve ser um membro do grupo de segurança especificado do Active Directory listado. Um administrador ou outro membro de grupo delegado do Active Directory com permissões adequadas para adicionar usuários a um grupo de segurança (por exemplo, administrador, operadores de conta) devem adicionar um objeto de usuário ao grupo ou grupo de segurança listado para que o usuário possa executar as funções listadas. <STRONG>(2)</STRONG> somente para fluxos de trabalho que o CsResponseGroupAdministrator atribuiu ao CsResponseGroupManager. <STRONG>(3)</STRONG> um gerente de grupo de resposta pode atribuir outro membro de CsResponseGroupManager a um fluxo de trabalho que o gerente atual já gerencia. <STRONG>(4)</STRONG> CsViewOnlyAdministrator só pode executar cmdlets do Shell de gerenciamento do Lync Server "Get" do Lync Server.



</div>

</div>

<div>

## <a name="response-group-configuration-prerequisites"></a>Requisitos de configuração do grupo de resposta

O grupo de resposta requer os seguintes componentes:

  - Serviço de aplicativos

  - Aplicativo Grupo de Resposta

  - Pacotes de idioma

  - Repositório de arquivos (para manter arquivos de áudio)

  - Serviços Web (inclui a ferramenta de configuração de grupo de resposta e o console de entrada e saída dos agentes)

Todos esses componentes são instalados por padrão quando você implanta o Enterprise Voice.

Talvez seja necessário executar as seguintes tarefas antes de configurar o grupo de resposta:

  - Habilite os usuários do Lync Server 2013 e do Enterprise Voice.

  - Modificar um arquivo de configuração para estar em conformidade com os Padrões de Processamento de Informação Federal (FIPS).

  - Modificar o agrupamento do banco de dados para suportar caracteres Yi, Meng, e Zang para nomes de fila e nomes de grupo de agentes.

<div>

## <a name="enabling-users"></a>Ativando usuários

A primeira etapa na configuração do grupo de resposta é criar grupos de agente. Antes de poder criar um grupo de agente, você deve habilitar os usuários que serão agentes para o grupo de resposta do Lync Server 2013 e Enterprise Voice. Habilitar usuários para o Lync Server 2013 normalmente é uma etapa na implantação do servidor Enterprise Edition Server ou Standard Edition Server. Para obter detalhes sobre como habilitar usuários do Lync Server 2013, consulte [desabilitar ou habilitar novamente a conta de usuário para o Lync server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md). A habilitação dos usuários para o Enterprise Voice geralmente é uma etapa na implantação do Enterprise Voice. Para obter detalhes, consulte [habilitar usuários do Enterprise Voice no Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).

</div>

<div>

## <a name="complying-with-fips-requirements"></a>Em conformidade com os requisitos FIPS

Essa seção se aplica a você apenas se sua organização precisar estar em conformidade com os Padrões de Processamento de Informações Federais (FIPS).

Para estar em conformidade com FIPS, você precisa modificar o nível de aplicativo do arquivo Web.config para utilizar um algoritmo de criptografia diferente após instalar os Serviços Web. Você precisa especificar que o ASP.NET utiliza o algoritmo do Padrão de Criptografia de Dados Triplo (3DES) para processar dados de estado de visualização. Para o aplicativo de grupo de resposta, esse requisito se aplica à ferramenta de configuração de grupo de resposta e ao console de entrada e saída do agente. Para obter detalhes sobre esse requisito, consulte o artigo 911722 da base de dados de conhecimento Microsoft, "você pode receber uma mensagem de erro ao acessar páginas da Web do ASP.NET com ViewState habilitado após a atualização do ASP.NET 1,1 [http://go.microsoft.com/fwlink/p/?linkId=196183](http://go.microsoft.com/fwlink/p/?linkid=196183)para o ASP.NET 2,0," at.

Para modificar o arquivo Web.config, faça o seguinte:

1.  Em um editor de texto como o Notepad, abra o arquivo Web.config de nível de aplicativo.

2.  No arquivo Web. config, localize a `<system.web>` seção.

3.  Adicione a seguinte `<machineKey>` seção à `<system.web>` seção:
    
        <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>

4.  Salve o arquivo Web.config.

5.  Reinicie o serviço de serviços de informações da Internet (IIS) executando o seguinte comando em um prompt de comando:
    
        iisreset

</div>

<div>

## <a name="supporting-yi-meng-and-zang-characters"></a>Suporte a caracteres Yi, Meng e Zang

Essa seção se aplica apenas se a sua organização precisar suportar caracteres Yi, Meng ou Zang.

<div>


> [!NOTE]  
> Para obter informações sobre o que são os caracteres Yi, Meng e Zang e por que eles podem ser importantes para a sua implantação, consulte as informações nos conjuntos <A href="http://go.microsoft.com/fwlink/p/?linkid=240223">http://go.microsoft.com/fwlink/p/?linkId=240223</A>de caracteres do GB18030.



</div>

Para suportar caracteres Yi, Meng ou Zang, você precisa modificar o agrupamento para o banco de dados Rgsconfig. Altere o agrupamento da coluna  **Nome** nas seguintes tabelas em cada banco de dados Rgsconfig:

  - dbo.AgentGroups

  - dbo.BusinessHours

  - dbo.HolidaySets

  - dbo.Queues

  - dbo.Workflows

Para SQL Server 2008 R2 e SQL Server 2012, use o agrupamento\_latim\_geral 100 (diferenciação de ênfase). Se você utiliza tal agrupamento, todos os nomes de objeto não diferenciam maiúsculas de minúsculas.

Você pode mudar o agrupamento utilizando o Microsoft SQL Server Management Studio. Para obter detalhes sobre como usar essa ferramenta, consulte "usando o SQL Server Management [http://go.microsoft.com/fwlink/p/?linkId=196184](http://go.microsoft.com/fwlink/p/?linkid=196184)Studio" em. Siga essas etapas para alterar o agrupamento:

1.  Certifique-se de que o SQL Server Management Studio está configurado para permitir alterações que precisam que as tabelas sejam recriadas. Para obter detalhes, consulte a caixa de diálogo "salvar (não permitido [http://go.microsoft.com/fwlink/p/?linkId=196186](http://go.microsoft.com/fwlink/p/?linkid=196186))" em. Para obter detalhes sobre como definir um agrupamento de colunas, consulte "como: definir o agrupamento de colunas (ferramentas de [http://go.microsoft.com/fwlink/p/?linkId=196185](http://go.microsoft.com/fwlink/p/?linkid=196185)banco de dados Visual)" em.

2.  Utilizando o Microsoft SQL Server Management Studio, conecte-se ao banco de dados Rgsconfig.

3.  Encontre a tabela que deseja alterar no banco de dados Rgsconfig, clique com o botão direito na tabela e em **Design**.

4.  Altere o agrupamento da coluna **Nome** e salve a tabela.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

