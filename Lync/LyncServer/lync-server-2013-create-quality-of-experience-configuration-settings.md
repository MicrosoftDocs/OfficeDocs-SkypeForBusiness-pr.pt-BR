---
title: 'Lync Server 2013: criar definições de configuração de qualidade de experiência'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Quality of Experience configuration settings
ms:assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521006(v=OCS.15)
ms:contentKeyID: 48184357
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a94b7183be9927267796d3e2adaed12b3b71eaf6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501628"
---
# <a name="create-quality-of-experience-configuration-settings-in-lync-server-2013"></a>Criar definições de configuração de qualidade de experiência no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-23_

Os atributos métricos da Qualidade da Experiência (QoE) rastreiam a qualidade das chamadas de áudio e vídeo feitas na organização, inclusive o número de pacotes de rede perdidos, o ruído de fundo e a quantidade de "jitter" (diferenças no atraso de pacotes). Esses atributos métricos são armazenados em um banco de dados separado de outros dados (como registros de detalhes das chamadas), permitindo a habilitação e desabilitação do QoE, independentemente de outros registros de dados.

Quando você instala o Microsoft Lync Server 2013, um único conjunto global de definições de configuração de QoE é criado para você. Os administradores também podem ter a opção de criar configurações personalizadas no escopo local. Sempre que estas configurações de escopo local são usadas, elas têm precedência sobre as configurações globais. Por exemplo, se você criar configurações de escopo de site para o site Redmond, essas configurações (em vez das configurações globais) serão usadas para gerenciar o QoE em Redmond.

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
<td><p>Identificador exclusivo das configurações a serem criadas. As definições de configuração de QoE só podem ser criadas no escopo do site.</p></td>
</tr>
<tr class="even">
<td><p>Habilitar o monitoramento de dados de QoE</p></td>
<td><p>EnableQoE</p></td>
<td><p>Especifica se os registros QoE serão coletados e salvos no banco de dados de monitoramento.</p></td>
</tr>
<tr class="odd">
<td><p>Habilitar a limpeza de dados de QoE</p></td>
<td><p>EnablePurging</p></td>
<td><p>Especifica se os registros serão removidos após a duração definida na propriedade <strong>manter dados de QoE para uma duração máxima (dias)</strong> .</p></td>
</tr>
<tr class="even">
<td><p>Manter dados de QoE por um período máximo (dias)</p></td>
<td><p>KeepQoEDataForDays</p></td>
<td><p>Número de dias que os dados de QoE serão armazenados antes de serem excluídos do banco de dados. Esse valor será ignorado se a limpeza estiver desabilitada.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> O cmdlet New-CsQoEConfiguration inclui opções adicionais não disponíveis no painel de controle do Lync Server. Para obter mais informações, consulte o tópico de ajuda <A href="https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration">New-CsQoEConfiguration</A> .



</div>

<div>

## <a name="to-create-qoe-configuration-settings-by-using-lync-server-control-panel"></a>Para criar definições de configuração de QoE usando o painel de controle do Lync Server

1.  Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e em **Dados da Qualidade da Experiência**.

4.  Na página **dados de qualidade da experiência** , clique em **novo**.

5.  Em **selecionar um site**, clique no site ao qual a política será aplicada e clique em **OK**.

6.  Em **nova configuração de qualidade de experiência**, faça o seguinte:
    
      - Selecione **habilitar monitoramento de dados de QoE** para ativar o monitoramento.
    
      - Selecione **habilitar limpeza de dados de QoE** para ativar a limpeza.
    
      - Em **manter QoE por duração máxima (dias)**, selecione o número máximo de dias durante os quais os registros de QoE devem ser mantidos.

7.  Clique em **Confirmar**.

</div>

<div>

## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Criar definições de configuração de QoE usando cmdlets do Windows PowerShell

Você pode criar definições de configuração de QoE usando o Windows PowerShell e o cmdlet New-CsQoEConfiguration. Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a>Para criar um novo conjunto de definições de configuração de QoE

  - Este comando cria uma nova coleção de definições de configuração de QoE aplicada ao site de Redmond:
    
        New-CsQoEConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>Para criar um novo conjunto de definições de configuração de QoE onde o monitoramento de QoE está desabilitado

  - Como nenhum parâmetro (além do parâmetro obrigatório Identity) foi especificado no comando anterior, o novo conjunto de definições de configurações usará os valores padrões para todas suas propriedades. Para criar configurações que usam valores de propriedade diferentes, basta incluir o parâmetro e o valor de parâmetro adequado. Por exemplo, para criar um conjunto de definições de configuração de qualidade de experiência que, por padrão, permitir desabilitar a gravação de QoE use um comando como este:
    
        New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a>Para especificar vários valores de propriedade ao criar um novo conjunto de definições de configuração de QoE

  - Você pode vários valores de propriedade incluindo vários parâmetros. Por exemplo, este comando define as novas configurações para manter os dados de QoE por 30 dias e limpar dados antigos às 3:00:
    
        New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3

</div>

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

