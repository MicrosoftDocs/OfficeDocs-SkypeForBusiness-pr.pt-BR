---
title: 'Lync Server 2013: criar definições de configuração de qualidade de experiência'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create Quality of Experience configuration settings
ms:assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521006(v=OCS.15)
ms:contentKeyID: 48184357
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 947fb50c057fdcc04fe7d1b30d25bc8f5a5f4a02
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829777"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-quality-of-experience-configuration-settings-in-lync-server-2013"></a>Criar definições de configuração de qualidade de experiência no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-23_

As métricas de Qualidade da Experiência (QoE) rastreiam a qualidade das chamadas de áudio e vídeo feitas na organização, inclusive o número de pacotes de rede perdidos, o ruído de fundo e a quantidade de tremulação (diferenças no atraso de pacotes). Essas métricas são armazenadas em um banco de dados separado de outros dados (como registros de detalhes das chamadas), permitindo a habilitação e desabilitação da QoE, independente de outros registros de dados.

Ao instalar o Microsoft Lync Server 2013, uma única coleção global de definições de configuração de QoE é criada para você. Os administradores também podem ter a opção de criar configurações personalizadas no escopo local. Sempre que essas configurações do escopo do site forem usadas, elas prevalecerão sobre as configurações globais. Por exemplo, se você criar configurações de escopo de site para o site da cidade de Redmond, essas configurações (em vez das globais) serão usadas para gerenciar a QoE em Redmond.

As definições de configuração de QoE podem ser criadas usando o painel de controle do Lync Server ou o cmdlet [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) . Se você estiver usando o painel de controle do Lync Server para criar novas configurações, as seguintes opções estarão disponíveis para você:


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
<td><p>Identificador exclusivo das configurações a serem criadas. As configurações de QoE só podem ser criadas no escopo do site.</p></td>
</tr>
<tr class="even">
<td><p>Habilitar monitoramento de dados de QoE</p></td>
<td><p>EnableQoE</p></td>
<td><p>Especifica se os registros QoE serão coletados e salvos no banco de dados de monitoramento.</p></td>
</tr>
<tr class="odd">
<td><p>Habilitar limpeza de dados de QoE</p></td>
<td><p>EnablePurging</p></td>
<td><p>Especifica se os registros serão apagados ao final do período definido na propriedade <strong>Manter dados de QoE por um período máximo de (dias)</strong>.</p></td>
</tr>
<tr class="even">
<td><p>Manter dados de QoE por um período máximo de (dias)</p></td>
<td><p>KeepQoEDataForDays</p></td>
<td><p>O número de dias durante os quais os dados de QoE permanecerão armazenados antes de serem apagados do banco de dados. Esse valor será ignorado se a limpeza estiver desabilitada.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> O cmdlet New-CsQoEConfiguration inclui opções adicionais que não estão disponíveis no painel de controle do Lync Server. Para obter mais informações, consulte o tópico da ajuda <A href="https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration">New-CsQoEConfiguration</A> .



</div>

<div>

## <a name="to-create-qoe-configuration-settings-by-using-lync-server-control-panel"></a>Para criar definições de configuração de QoE usando o painel de controle do Lync Server

1.  Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Monitoramento e arquivamento** e em **Dados de Qualidade da Experiência**.

4.  Na página **Dados de Qualidade da Experiência**, clique em **Novo**.

5.  Em **Selecionar um site**, clique no site ao qual a política deverá ser aplicada e depois em **OK**.

6.  Em **Criar Nova Configuração da Qualidade da Experiência**, faça o seguinte:
    
      - Selecione **Habilitar monitoramento de dados de QoE** para habilitar o monitoramento.
    
      - Selecione **Habilitar limpeza de dados de QoE** para habilitar a limpeza.
    
      - Em **Manter dados de QoE por um período máximo de (dias)**, selecione o número máximo de dias durante os quais os registros de QoE deverão ser mantidos.

7.  Clique em **Confirmar**.

</div>

<div>

## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Criar definições de configuração de QoE usando cmdlets do Windows PowerShell

Você pode criar definições de configuração de QoE usando o Windows PowerShell e o cmdlet New-CsQoEConfiguration. Você pode executar esse cmdlet a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a>Para criar um novo conjunto de configurações de QoE

  - Este comando cria um novo conjunto de configurações de QoE que será aplicado ao site de Redmond:
    
        New-CsQoEConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>Para criar um conjunto de configurações de QoE com o monitoramento de QoE desabilitado

  - Como nenhum parâmetro (além do parâmetro Identity obrigatório) foi especificado no comando anterior, o novo conjunto de configurações usará os valores padrão para todas as respectivas propriedades. Para criar configurações que usem outros valores de propriedade, basta incluir o parâmetro e o valor de parâmetro desejados. Por exemplo, para criar um conjunto de configurações de QoE que, por padrão, permita a desabilitação do registro de QoE, use um comando como o seguinte:
    
        New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a>Para especificar vários valores de propriedade ao criar um novo conjunto de configurações de QoE

  - Você pode especificar vários valores de propriedade incluindo vários parâmetros. Por exemplo, o seguinte comando define as novas configurações para manter os dados de QoE por 30 dias e para apagar os dados antigos às 3:00 AM:
    
        New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3

</div>

Para obter mais informações, consulte o tópico da ajuda para o cmdlet [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

