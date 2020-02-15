---
title: 'Lync Server 2013: criar ou modificar um conjunto de definições de configuração de CDR'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of CDR configuration settings
ms:assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721878(v=OCS.15)
ms:contentKeyID: 49733812
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 234225364c8701432271c2cf5a48c9bb6d403103
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035627"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-lync-server-2013"></a>Criar ou modificar um conjunto de definições de configuração de CDR no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-23_

O registro de detalhes da chamada (CDR) permite rastrear o uso de coisas como sessões de mensagem instantânea ponto a ponto, chamadas de telefone Protocolo Voz por Internet (VoIP) e chamadas de conferência. Este dados de uso inclui informações sobre quem ligou para quem, quando realizou a ligação e quanto tempo foi a conversa.

Ao instalar o Microsoft Lync Server 2013, um único conjunto global de definições de configuração de CDR é criado para você. Os administradores também podem ter a opção de criar configurações personalizadas no escopo local. Sempre que estas configurações de escopo local são usadas, elas têm precedência sobre as configurações globais. Por exemplo, se você criar configurações de escopo local para o local Redmond, estas configurações (ao invés das configurações globais) serão usadas para gerenciar CDR em Redmond.

Você pode criar definições de configuração de CDR usando o painel de controle do Lync Server ou o cmdlet [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) . Você pode usar o painel de controle do Lync Server ou o cmdlet [set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) para modificar as configurações existentes. Se você estiver usando o painel de controle do Lync Server para criar ou modificar as configurações, as seguintes opções estarão disponíveis para você:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Configuração de UI</th>
<th>Parâmetro do PowerShell</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nome</p></td>
<td><p>Identidade</p></td>
<td><p>Identificador exclusivo das definições de configuração CDR sendo criada. Estas configurações podem ser criadas apenas no escopo local.</p></td>
</tr>
<tr class="even">
<td><p>Habilitar monitoramento de CDRs</p></td>
<td><p>EnableCDR</p></td>
<td><p>Indica se o CDR está ou não habilitado.</p></td>
</tr>
<tr class="odd">
<td><p>Habilitar exclusão de CDRs</p></td>
<td><p>EnablePurging</p></td>
<td><p>Indica se os registros CDR serão ou não periodicamente excluídos do banco de dados de CDR.</p></td>
</tr>
<tr class="even">
<td><p>Manter CDRs pela duração máxima (dias)</p></td>
<td><p>KeepCallDetailForDays</p></td>
<td><p>Indica o número de dias que os registros CDR serão mantidos no banco de dados de CDR. Qualquer registro anterior ao número de dias especificado será automaticamente excluído. (Observe que excluir ocorrerá apenas se a exclusão tiver habilitada.)</p></td>
</tr>
<tr class="odd">
<td><p>Manter os dados do relatório de erro pela duração máxima (dias)</p></td>
<td><p>KeepErrorReportForDays</p></td>
<td><p>Indica o número de dias que os relatórios de erros do CDR são mantidos. Qualquer relatório mais antigo do que o número de dias especificado será automaticamente excluído. Os relatórios de CDR são relatórios de diagnósticos, carregados por aplicativos cliente.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Os cmdlets New-CsCdrConfiguration e Set-CsCdrConfiguration incluem opções adicionais não disponíveis no painel de controle do Lync Server. Consulte os tópicos de ajuda <A href="https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration">New-CsCdrConfiguration</A> e <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration">set-CsCdrConfiguration</A> para obter mais informações.



</div>

<div>

## <a name="to-create-cdr-configuration-settings-by-using-lync-server-control-panel"></a>Para criar definições de configuração de CDR usando o painel de controle do Lync Server

1.  No painel de controle do Lync Server, clique em **monitoramento e arquivamento**.

2.  Na guia **registro de detalhes das chamadas** , clique em **novo**.

3.  Na caixa de diálogo **Selecionar um local**, selecione o local onde as novas definições de configuração devem ser criadas. Se a caixa de diálogo estiver vazia, isto significa que todos os seus locais já foram atribuídos com um conjunto de definições de configuração CDR. Cada local é limitado para um único conjunto. Neste caso, é possível excluir e recriar as configurações ou apenas modificar as configurações existentes.

4.  Na caixa de diálogo **Nova configuração CDR**, faça as seleções desejadas e clique em **Confirmar**.

</div>

<div>

## <a name="to-modify-existing-cdr-configuration-settings-by-using-lync-server-control-panel"></a>Para modificar as definições de configuração de CDR existentes usando o painel de controle do Lync Server

1.  No painel de controle do Lync Server, clique em **monitoramento e arquivamento**.

2.  Clique duas vezes no conjunto de configurações a ser modificado ou selecione o conjunto, clique em **Editar** e em **Exibir detalhes**. Observe que você pode apenas modificar um único conjunto por vez. Para fazer as mesmas alterações em várias coleções, use o Shell de gerenciamento do Lync Server.

3.  Na caixa de diálogo**Editar configuração de CDR**, certifique-se de fazer as seleções desejadas e clique em **Confirmar**.

</div>

<div>

## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Criar definições de configuração de CDR usando cmdlets do Windows PowerShell

Você pode criar definições de configuração de CDR também podem ser criadas usando o Windows PowerShell e o cmdlet **New-CsCdrConfiguration** . Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.

<div>

## <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a>Para criar um novo conjunto de definições de configuração CDR

  - Este comando cria um novo conjunto de definições de configuração CDR aplicadas ao local Redmond:
    
        New-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a>Para criar um conjunto de definições de configuração CDR que desabilitam o registro de detalhes da chamada

  - Como nenhum parâmetro (além do parâmetro obrigatório Identity) foi especificado no comando anterior, o novo conjunto de definições de configurações usará os valores padrões para todas suas propriedades. Para criar configurações que usam valores de propriedade diferentes, basta incluir o parâmetro e o valor de parâmetro adequado. Por exemplo, para criar um conjunto de definições de configuração de Detalhe da Chamada que, por padrão, permite desabilitar o registro de Detalhes da chamada, use um comando como este:
    
        New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a>Para especificar vários valores de propriedade ao criar um novo conjunto de definições de configuração CDR

  - É possível modificar vários valores de propriedade incluindo vários parâmetros. Por exemplo, este comando define as novas configurações para manter registros de Detalhe da Chamada por 30 dias e relatórios de erro por 90 dias:
    
        New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90

</div>

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

