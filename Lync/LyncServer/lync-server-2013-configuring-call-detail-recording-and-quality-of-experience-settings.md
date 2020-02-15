---
title: Configurando a gravação de detalhes da chamada e as configurações de qualidade da experiência
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring call detail recording and Quality of Experience settings
ms:assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204621(v=OCS.15)
ms:contentKeyID: 48183223
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8382d95ebc1c90a46ab1edee8248b7892e297ea2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046234"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-call-detail-recording-and-quality-of-experience-settings-in-lync-server-2013"></a>Configurando a gravação de detalhes da chamada e as configurações de qualidade da experiência no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-17_

Depois de associar um repositório de monitoramento a um pool de front-ends, configurar o repositório de monitoramento e, em seguida, instalar e configurar o SQL Server Reporting Services e os relatórios de monitoramento, você poderá gerenciar o CDR (registro de detalhes de chamadas) e o QoE (qualidade da experiência) monitoramento usando o Shell de gerenciamento do Lync Server. Os cmdlets do Shell de gerenciamento do Lync Server permitem habilitar e desabilitar o monitoramento de CDR e/ou QoE para um determinado site ou para toda a sua implantação do Lync Server; Isso pode ser feito com um comando tão simples quanto:

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $False

Ao instalar o Microsoft Lync Server 2013, você também instalará um conjunto predefinido de definições de configuração global para CDR e QoE. Os valores padrão para algumas das configurações usados com mais frequência pelo Registro de Detalhes das Chamadas são exibidos na tabela a seguir:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Propriedade</th>
<th>Descrição</th>
<th>Valor padrão</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>EnableCDR</p></td>
<td><p>Indica se o CDR está habilitado ou não. Se for Verdadeiro, todos os registros de CDR serão coletados e gravados no banco de dados de monitoramento.</p></td>
<td><p>True</p></td>
</tr>
<tr class="even">
<td><p>EnablePurging</p></td>
<td><p>Indica se os registros CDR serão excluídos periodicamente do banco de dados. Se for Verdadeiro, os registros serão excluídos após o período especificado pelas propriedades KeepCallDetailForDays (para registros CDR) e KeepErrorReportForDays (para erros de CDR). Se for Falso, os registros CDR serão mantidos indefinidamente.</p></td>
<td><p>True</p></td>
</tr>
<tr class="odd">
<td><p>KeepCallDetailForDays</p></td>
<td><p>Indica o número de dias durante os quais os registros CDR serão mantidos no banco de dados; quaisquer registros mais antigos do que o número especificado de dias serão automaticamente excluídos. No entanto, isso ocorrerá somente se a exclusão tiver sido habilitada.</p>
<p>KeepCallDetailForDays pode ser definido como qualquer valor inteiro entre 1 e 2562 dias (aproximadamente 7 anos).</p></td>
<td><p>60 dias</p></td>
</tr>
<tr class="even">
<td><p>KeepErrorReportForDays</p></td>
<td><p>Indica o número de dias durante os quais esses relatórios de erro CDR serão mantidos; quaisquer relatórios mais antigos do que o número especificado de dias serão automaticamente excluídos. Os relatórios de erros do CDR são relatórios de diagnóstico carregados por aplicativos cliente como o Microsoft Lync 2013.</p>
<p>É possível definir essa propriedade como qualquer valor inteiro entre 1 e 2562 dias.</p></td>
<td><p>60 dias</p></td>
</tr>
</tbody>
</table>


Da mesma forma, os valores padrão para as configurações de QoE selecionadas são exibidas nesta tabela:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Propriedade</th>
<th>Descrição</th>
<th>Valor padrão</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>EnableQoE</p></td>
<td><p>Indica se o monitoramento de QoE está habilitado ou não. Se for Verdadeiro, todos os registros de QoE serão coletados e gravados no banco de dados de monitoramento.</p></td>
<td><p>True</p></td>
</tr>
<tr class="even">
<td><p>EnablePurging</p></td>
<td><p>Indica se os registros de QoE serão excluídos periodicamente do banco de dados. Se for Verdadeiro, os registros serão excluídos após o período especificado pela propriedade KeepQoEDataForDays. Se for Falso, os registros de QoE serão mantidos indefinidamente.</p></td>
<td><p>True</p></td>
</tr>
<tr class="odd">
<td><p>KeepQoEDataForDays</p></td>
<td><p>Indica o número de dias durante os quais os registros de QoE serão mantidos no banco de dados; quaisquer registros mais antigos do que o número especificado de dias serão automaticamente excluídos. No entanto, isso ocorrerá somente se a exclusão tiver sido habilitada.</p>
<p>KeepCallDetailForDays pode ser definido como qualquer valor inteiro entre 1 e 2562 dias.</p></td>
<td><p>60 dias</p></td>
</tr>
</tbody>
</table>


Se for necessário modificar essas configurações globais, você poderá fazer isso usando os cmdlets Set-CsCdrConfiguration e Set-CsQoEConfiguration. Por exemplo, esse comando (executado a partir do Shell de Gerenciamento do Lync Server) desabilita o monitoramento de CDR no escopo global; isso é feito configurando a propriedade EnableCDR como Falso ($False):

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $False

Observe que a desabilitação do monitoramento não desassocia o repositório de monitoramento do pool Front-End, nem desinstala ou afeta de outra forma o banco de dados de monitoramento backend. Quando você usa o Shell de gerenciamento do Lync Server para desabilitar o monitoramento de CDR ou QoE, você realmente impede que o Lync Server colete e arquive dados de monitoramento temporariamente. Se quiser continuar, nesse caso, a coleta e o arquivamento de dados CDR, tudo o que você precisa fazer é definir a propriedade EnableCDR de volta para Verdadeiro ($True):

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

Da mesma maneira, esse comando desabilita a exclusão de registros QoE no escopo global:

    Set-CsQoEConfiguration -Identity "global" -EnablePurging $False

Além das configurações globais, as configurações de CDR e QoE podem ser atribuídas ao escopo do site. Isso fornece flexibilidade de gerenciamento adicional quando se trata de monitoramento; por exemplo, um administrador pode habilitar o monitoramento de CDR para o site Redmond, mas desabilitar o monitoramento de CDR para o site Dublin. Para criar novas configurações de CDR no escopo do site, use um comando parecido com o seguinte:

    New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

Lembre-se de que as configurações definidas no escopo do site têm precedência sobre as configurações definidas no escopo global. Por exemplo, suponha que o monitoramento CDR esteja habilitado no escopo global, mas desabilitado no escopo do site (para o site Redmond). Isso significa que as informações de registro de detalhe da chamada não serão arquivadas para usuários no site Redmond. No entanto, usuários em outros sites (ou seja, usuários gerenciados pelas configurações globais em vez das configurações do site Redmond) terão suas informações de registro de detalhe da chamada arquivadas.

As novas configurações de QoE podem ser criadas no escopo do site usando um comando como este:

    New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15

Para obter mais informações, digite os seguintes comandos no Shell de gerenciamento do Lync Server:

    Get-Help New-CsCdrConfiguration | more
    Get-Help Set-CsCdrConfiguration | more
    Get-Help New-CsQoEConfiguration | more
    Get-Help Set-CsQoEConfiguration | more

</div>

<span> </span>

</div>

</div>

</div>

