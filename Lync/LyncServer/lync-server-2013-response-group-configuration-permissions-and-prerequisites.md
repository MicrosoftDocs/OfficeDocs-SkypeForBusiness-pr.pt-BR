---
title: 'Lync Server 2013: permissões e pré-requisitos de configuração de grupo de resposta'
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
ms.openlocfilehash: 7289b8818a6193efa867ab0a8671abf6d4701f7c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511738"
---
# <a name="response-group-configuration-permissions-and-prerequisites-in-lync-server-2013"></a>Permissões e pré-requisitos de configuração de grupo de resposta no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-05_

O Grupo de Resposta é um recurso de gerenciamento de chamadas do Enterprise Voice. Este tópico descreve o que é preciso ter para que você possa configurar o Grupo de Resposta, bem como as credenciais administrativas e as permissões necessárias para a execução de tarefas de configuração.

Esta seção supõe que você leu a documentação de planejamento relacionada ao Grupo de Resposta. Para obter detalhes, consulte [Planning for Call Management Features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md) na documentação de planejamento.

<div>

## <a name="configuration-tools-and-administrative-roles"></a>Ferramentas de configuração e funções administrativas

É possível usar as seguintes ferramentas administrativas para configurar o Grupo de Resposta:

  - Painel de controle do Lync Server

  - Ferramenta de configuração do grupo de resposta

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
<td><p><strong>À csresponsegroupmanager</strong></p></td>
<td> </td>
<td><p>√ (2)</p></td>
<td><p>√ (3)</p></td>
<td><p>√ (3)</p></td>
<td><p>√ (3)</p></td>
<td><p>√ (3)</p></td>
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
<td><p>√ (4)</p></td>
<td><p>√ (4)</p></td>
<td><p>√ (4)</p></td>
<td><p>√ (4)</p></td>
<td><p>√ (4)</p></td>
<td><p>√ (4)</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <STRONG>(1)</STRONG> um objeto de usuário dos serviços de domínio Active Directory deve ser um membro do grupo de segurança do Active Directory especificado listado. Um administrador ou outro membro do grupo do Active Directory delegado com as permissões apropriadas para adicionar usuários a um grupo de segurança (por exemplo, administrador, operadores de conta) deve adicionar um objeto de usuário ao grupo ou grupo de segurança listado para que o usuário possa executar as funções listadas. <STRONG>(2)</STRONG> somente para fluxos de trabalho que o CsResponseGroupAdministrator atribuiu ao à csresponsegroupmanager. <STRONG>(3)</STRONG> um gerente de grupo de resposta pode atribuir outro membro de à csresponsegroupmanager a um fluxo de trabalho que o gerente atual já gerencia. <STRONG>(4)</STRONG> o CsViewOnlyAdministrator pode executar apenas o verbo "Get" do Lync Server Management Shell cmdlets.



</div>

</div>

<div>

## <a name="response-group-configuration-prerequisites"></a>Pré-requisitos da configuração do Grupo de Resposta

O Grupo de Resposta requer os seguintes componentes:

  - Serviço de aplicativos

  - Aplicativo Grupo de Resposta

  - Pacotes de idiomas

  - Repositório de arquivos (para armazenar arquivos de áudio)

  - Serviços Web (inclui a ferramenta de configuração de grupo de resposta e o console de entrada e saída dos agentes)

Todos estes componentes são instalados por padrão ao implantar o Enterprise Voice.

Talvez seja necessário executar as seguintes tarefas antes de configurar o grupo de resposta:

  - Habilitar usuários para o Lync Server 2013 e Enterprise Voice.

  - Modificar um arquivo de configuração para ser compatível com o FIPS (Federal Information Processing Standards).

  - Modificar o agrupamento de banco de dados para oferecer suporte a caracteres Yi, Meng e Zang para nomes de fila e nomes de grupo de agente.

<div>

## <a name="enabling-users"></a>Permitir usuários

A primeira etapa da configuração do grupo de resposta é criar grupos de agentes. Antes de poder criar um grupo de agentes, você deve habilitar os usuários que serão agentes para o grupo de resposta do Lync Server 2013 e Enterprise Voice. Habilitar usuários para o Lync Server 2013 normalmente é uma etapa na implantação do servidor Enterprise Edition ou do servidor Standard Edition. Para obter detalhes sobre como habilitar usuários para o Lync Server 2013, confira [desabilitar ou reabilitar a conta de usuário do Lync server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md). Habilitar usuários para Enterprise Voice geralmente é uma etapa na implantação de Enterprise Voice. Para obter detalhes, consulte [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).

</div>

<div>

## <a name="complying-with-fips-requirements"></a>Conformidade com os requisitos FIPS

Esta seção somente se aplica a você sea  sua organização precisa cumprir com o FIPS (Federal Information Processing Standards).

Para ser compatível com o FIPS, você precisará modificar o arquivo Web.config de nível de aplicativo para usar um algoritmo de criptografia diferente depois de instalar os serviços da Web. Você precisa especificar que o ASP.NET usa o algoritmo Triple Data Encryption Standard (3DES) para processar os dados de estado de exibição. Para o aplicativo grupo de resposta, esse requisito se aplica à ferramenta de configuração de grupo de resposta e ao console de entrada e saída do agente. Para obter detalhes sobre esse requisito, consulte o artigo 911722 da base de dados de conhecimento da Microsoft, "você pode receber uma mensagem de erro ao acessar as páginas da Web do ASP.NET que possuem ViewState habilitado após a atualização do ASP.NET 1,1 para o ASP.NET 2,0" em [https://go.microsoft.com/fwlink/p/?linkId=196183](https://go.microsoft.com/fwlink/p/?linkid=196183) .

Para modificar o arquivo Web.config, faça o seguinte:

1.  Em um editor de texto como o Notepad, abra o arquivo Web.config de nível de aplicativo.

2.  No arquivo Web.config, localize a `<system.web>` seção.

3.  Adicione a seguinte `<machineKey>` seção na `<system.web>` seção:
    
        <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>

4.  Salve o arquivo Web.config.

5.  Reinicie o serviço serviços de informações da Internet (IIS) executando o seguinte comando em um prompt de comando:
    
        iisreset

</div>

<div>

## <a name="supporting-yi-meng-and-zang-characters"></a>Suporte aos caracteres Yi, Meng e Zang

Esta seção se aplica a você somente se a sua organização precisa oferecer suporte a caracteres Yi, Meng ou Zang.

<div>


> [!NOTE]  
> Para obter informações sobre o que os caracteres Yi, Meng e Zang são e por que eles podem ser importantes para sua implantação, consulte as informações nos conjuntos de caracteres do GB18030 <A href="https://go.microsoft.com/fwlink/p/?linkid=240223">https://go.microsoft.com/fwlink/p/?linkId=240223</A> .



</div>

Para oferecer suporte a caracteres Yi, Meng ou Zang, você precisará modificar o agrupamento para o banco de dados Rgsconfig. Altere o agrupamento da coluna **Nome** nas seguintes tabelas em cada banco de dados Rgsconfig:

  - dbo. AgentGroups

  - dbo. BusinessHours

  - dbo. HolidaySets

  - dbo. Filas

  - dbo. Fluxos

Para o SQL Server 2008 R2 e o SQL Server 2012, use \_ o \_ agrupamento latim geral 100 (diferenciação de ênfase). Se você usar esse agrupamento, todos os nomes de objeto não se diferenciarão entre maiúsculas e minúsculas.

Você pode alterar o agrupamento usando o Microsoft SQL Server Management Studio. Para obter detalhes sobre como usar essa ferramenta, consulte "usando o SQL Server Management Studio" em [https://go.microsoft.com/fwlink/p/?linkId=196184](https://go.microsoft.com/fwlink/p/?linkid=196184) . Siga essas etapas para alterar o agrupamento:

1.  Certifique-se de que o SQL Server Management Studio está configurado para permitir alterações que precisam que as tabelas sejam recriadas. Para obter detalhes, consulte "caixa de diálogo Salvar (não permitido)" em [https://go.microsoft.com/fwlink/p/?linkId=196186](https://go.microsoft.com/fwlink/p/?linkid=196186) . Para obter detalhes sobre como configurar um agrupamento de colunas, consulte "como definir o agrupamento de colunas (Visual Database Tools)" em [https://go.microsoft.com/fwlink/p/?linkId=196185](https://go.microsoft.com/fwlink/p/?linkid=196185) .

2.  Usando o Microsoft SQL Server Management Studio, conecte-se com o banco de dados Rgsconfig.

3.  Encontre a tabela que você deseja alterar no banco de dados Rgsconfig, clique com o botão direito na tabela e clique em **Design**.

4.  Altere o agrupamento da coluna **Nome** e salve a tabela.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

