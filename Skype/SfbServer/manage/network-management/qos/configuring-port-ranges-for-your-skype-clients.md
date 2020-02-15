---
title: Configurando intervalos de porta e uma política de qualidade de serviço para seus clientes
ms.reviewer: ''
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Este artigo descreve como configurar intervalos de porta para seus clientes e configurar as políticas de qualidade de serviço no Skype for Business Server para clientes que executam o Windows 10.
ms.openlocfilehash: 95fe768333a01aff165e74eec334f14bf23d69dc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045884"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a>Configurando intervalos de portas e uma política de qualidade de serviço para seus clientes no Skype for Business Server

Este artigo descreve como configurar intervalos de porta para seus clientes e configurar as políticas de qualidade de serviço no Skype for Business Server para clientes que executam o Windows 10.

## <a name="configure-port-ranges"></a>Configurar intervalos de porta

Por padrão, os aplicativos cliente do Skype for Business podem usar qualquer porta entre as portas 1024 e 65535 quando envolvido em uma sessão de comunicação; Isso ocorre porque intervalos de portas específicos não são automaticamente habilitados para clientes. Para poder usar a Qualidade do Serviço, no entanto, você precisará reatribuir os vários tipos de tráfego (áudio, vídeo, mídia, compartilhamento de aplicativos e transferência de arquivos) para uma série de intervalos de porta únicos. Isto pode ser realizado usando o cmdlet Set-CsConferencingConfiguration.

> [!NOTE]  
> Os usuários finais não podem fazer essas alterações por conta própria. As alterações de porta só podem ser feitas por administradores usando o cmdlet Set-CsConferencingConfiguration.


Você pode determinar quais intervalos de portas são usados atualmente para sessões de comunicação executando o seguinte comando no Shell de gerenciamento do Skype for Business Server:

    Get-CsConferencingConfiguration

Supondo que você não tenha feito nenhuma alteração nas configurações de conferência desde que você instalou o Skype for Business Server, você deve obter as informações que incluem estes valores de propriedade:

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

Se você verificar o resultado anterior, você verá duas coisas de importância. Primeiro, a propriedade ClientMediaPortRangeEnabled é definida para False:

    ClientMediaPortRangeEnabled : False

Isso é importante porque, quando essa propriedade é definida como false, os clientes do Skype for Business usarão qualquer porta disponível entre as portas 1024 e 65535 quando estiverem envolvidos em uma sessão de comunicação; Isso é verdadeiro independentemente de qualquer outra configuração de porta (por exemplo, ClientMediaPort ou ClientVideoPort). Se você deseja restringir o uso para um conjunto de portas especificado (e isso é algo que você deseja fazer se planejar a implementação da qualidade de serviço), primeiro você deve habilitar os intervalos de porta de mídia do cliente. Isso pode ser feito usando o seguinte comando do Windows PowerShell:

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

O comando anterior habilita os intervalos de porta de mídia do cliente para o conjunto global de definições de configuração de conferência; no entanto, estas configurações também podem ser aplicadas para o escopo local e/ou de serviço (apenas para o serviço do Servidor de Conferência). Para habilitar os intervalos de porta de mídia do cliente para um site ou servidor específico, defina a Identidade deste site ou servidor ao chamar Set-CsConferencingConfiguration:

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

Em alternativa, é possível usar este comando para habilitar simultaneamente intervalos de portas para todas as suas definições de configuração de conferência:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

A segunda coisa importante que você observará é o resultado de amostra mostrando que, por padrão, o conjunto de intervalos da porta de mídia para cada tipo de tráfego de rede são idênticos:

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

Para poder implementar o QoS, cada um destes intervalos de porta precisarão ser exclusivos. Por exemplo, você pode configurar os intervalos de porta desta forma:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de Tráfego do Cliente</th>
<th>Início da Porta</th>
<th>Intervalo da Porta</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Áudio</p></td>
<td><p>50020</p></td>
<td><p>508</p></td>
</tr>
<tr class="even">
<td><p>Vídeo</p></td>
<td><p>58000</p></td>
<td><p>508</p></td>
</tr>
<tr class="odd">
<td><p>Compartilhamento de aplicativo</p></td>
<td><p>42000</p></td>
<td><p>508</p></td>
</tr>
<tr class="even">
<td><p>Transferência de arquivos</p></td>
<td><p>42020</p></td>
<td><p>508</p></td>
</tr>
</tbody>
</table>


Na tabela anterior, os intervalos da porta do cliente representam um subconjunto dos intervalos de porta configurados para seus servidores. Por exemplo, nos servidores, o compartilhamento de aplicativos foi configurado para usar as portas 40803 a 49151; nos computadores clientes, o compartilhamento de aplicativos é configurado para usar as portas 42000 a 42019. Isso também é feito principalmente para tornar a administração da QoS mais fácil: as portas do cliente não precisam representar um subconjunto das portas usadas no servidor. (Por exemplo, nos computadores cliente, você poderia configurar o compartilhamento de aplicativos para usar, digamos, as portas 10000 a 10019.) No entanto, é recomendável que você faça seus intervalos de porta de cliente um subconjunto de intervalos de porta de servidor.

Além disso, você pode ter notado que 8348 portas foram configuradas para compartilhamento de aplicativos nos servidores, mas apenas 20 portas foram reservadas para o compartilhamento de aplicativos nos clientes. Isso também é recomendado, mas não é uma regra difícil e rápida. Em geral, você pode considerar cada porta disponível para representar uma única sessão de comunicação: se você tiver 100 portas disponíveis em um intervalo de porta, isso significa que o computador em questão pode participar, no máximo, 100 sessões de comunicação em um determinado momento. Como os servidores provavelmente farão parte de muito mais conversas do que os clientes, faz sentido abrir muito mais portas em servidores do que em clientes. A definição de 20 portas para compartilhamento de aplicativos em um cliente significa que um usuário pode participar de 20 sessões de compartilhamento de aplicativos no dispositivo especificado e todos ao mesmo tempo. Isso deve ser suficiente para a grande maioria dos seus usuários.

Para atribuir os intervalos de portas precedentes à sua coleção global de definições de configuração de conferência, você pode usar o seguinte comando do Shell de gerenciamento do Skype for Business Server:

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

Em alternativa, use este comando para atribuir estes mesmos intervalos de porta para todas suas definições de configuração de conferência:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

Os usuários individuais devem fazer logoff do Skype for Business e, em seguida, fazer logon novamente para que essas alterações entrem em vigor.

> [!NOTE]  
> Também é possível habilitar intervalos de porta da mídia do cliente e atribuir estes intervalos de porta usando um único comando. Por exemplo:<BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a>Configurar políticas de qualidade de serviço para clientes em execução no Windows 10

Além de especificar intervalos de portas para uso pelos clientes do Skype for Business, você também deve criar políticas de qualidade de serviço separadas que serão aplicadas aos computadores cliente. (As políticas de qualidade de serviço criadas para servidores de conferência, aplicativo e mediação não devem ser aplicadas aos computadores cliente.) Essas informações se aplicam somente a computadores que executam o cliente Skype for Business e o Windows 10.

O exemplo a seguir usa esse conjunto de intervalos de porta para criar uma política de áudio e uma política de vídeo:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de Tráfego do Cliente</th>
<th>Início da Porta</th>
<th>Intervalo da Porta</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Áudio</p></td>
<td><p>50020</p></td>
<td><p>508</p></td>
</tr>
<tr class="even">
<td><p>Vídeo</p></td>
<td><p>58000</p></td>
<td><p>508</p></td>
</tr>
<tr class="odd">
<td><p>Compartilhamento de aplicativo</p></td>
<td><p>42000</p></td>
<td><p>508</p></td>
</tr>
<tr class="even">
<td><p>Transferência de arquivos</p></td>
<td><p>42020</p></td>
<td><p>508</p></td>
</tr>
</tbody>
</table>

Para criar uma política de áudio de qualidade de serviço para computadores com Windows 10, primeiro faça logon em um computador onde o Group Policy Management tenha sido instalado. Abra gerenciamento de política de grupo (clique em **Iniciar**, aponte para **Ferramentas administrativas**e clique em **Gerenciamento de política de grupo**) e conclua o procedimento a seguir:

1.  No Gerenciamento de Política de Grupo, localize o contêiner em que a nova política deve ser criada. Por exemplo, se todos os seus computadores clientes estiverem localizados em um UO chamado clientes, a nova política deverá ser criada na OU do cliente.

2.  Clique com o botão direito do mouse no contêiner apropriado e clique em **criar um GPO neste domínio e vinculá-lo aqui**.

3.  Na caixa de diálogo **novo GPO** , digite um nome para o novo objeto de política de grupo na caixa **nome** e clique em **OK**.

4.  Clique com o botão direito do mouse na política recém-criada e clique em **Editar**.

5.  No editor de gerenciamento de política de grupo, expanda **configuração do computador**, expanda **configurações do Windows**, clique com o botão direito do mouse em **QoS baseada em política**e clique em **criar nova política**.

6.  Na caixa de diálogo **QoS baseada em política** , na página de abertura, digite um nome para a nova política na caixa **nome** . Selecione **Especificar valor de DSCP** e defina o valor como **46**. Deixe a opção **Especificar Taxa de Aceleração de Saída** desmarcada e clique em **Avançar**.

7.  Na próxima página, selecione **somente aplicativos com esse nome executável**, digite **Lync. exe** como o nome e clique em **Avançar**. Essa configuração instrui a política a priorizar apenas o tráfego de correspondência do cliente Skype for Business.

8.  Na terceira página, certifique-se de que **todos os endereços IP de origem** e de **destino** estejam selecionados e clique em **Avançar**. Essas duas configurações garantem que os pacotes serão gerenciados independente de qual computador (endereço IP) tenha os enviado e de qual computador (endereço IP) os receberá.

9.  Na página quatro, selecione **TCP e UDP** na lista suspensa **Selecione o protocolo ao qual esta política de QoS se aplica**. TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) são os dois protocolos de rede mais comumente usados pelo Skype for Business Server e seus aplicativos cliente.

10. No cabeçalho **Especifique o número da porta de origem**, selecione **Desta porta ou intervalo de origem**. Na caixa de texto acompanhante, digite o intervalo de porta reservado para transmissões de áudio. Por exemplo, se você reservou portas 50020 através de portas 50039 para tráfego de áudio, insira o intervalo de portas usando este formato: **50020:50039**. Clique em **Concluir**.

Depois de criar a política de QoS para o áudio, você deve criar uma segunda política para vídeo. Para criar uma política para vídeo, siga o mesmo procedimento básico da criação da política de áudio, fazendo as seguintes substituições:

  - Use um nome de política diferente (e exclusivo).

  - Defina o valor DSCP para **34** em vez de 46. (Conforme observado anteriormente, não é necessário usar o valor de DSCP 34; você deve apenas atribuir um valor de DSCP diferente daquele usado para áudio.)

  - Use o intervalo de porta configurado anteriormente para tráfego de vídeo. Por exemplo, se você reservou portas de 58000 a 58019 para vídeo, defina o intervalo de porta para: **58000:58019**.

Se você decidir criar uma política para gerenciar o tráfego de compartilhamento de aplicativos, faça estas substituições:

  - Use um nome de política diferente (e exclusivo) (por exemplo, **compartilhamento de aplicativos do Skype for Business Server**).

  - Defina o valor DSCP para **24** em vez de 46. (Novamente, esse valor não precisa ser 24; ele simplesmente deve ser diferente dos valores de DSCP usados para áudio e vídeo.)

  - Use o intervalo de porta configurado anteriormente para tráfego de vídeo. Por exemplo, se você reservou as portas de 42000 a 42019 para compartilhamento de aplicativos, defina o intervalo de porta para: **42000:42019**.

Para uma política de transferência de arquivos:

  - Use um nome de política diferente (e exclusivo) (por exemplo, **transferências de arquivo do Skype for Business Server**).

  - Defina o valor de DSCP para **14**. (Novamente, esse valor não precisa ser 14; ele simplesmente deve ser um código DSCP exclusivo.)

  - Use o intervalo de portas configurado anteriormente para o aplicativo. Por exemplo, se você reservou as portas de 42020 a 42039 para compartilhamento de aplicativos, defina o intervalo de porta para: **42020:42039**.

As novas políticas criadas não terão efeito até que a política de grupo tenha sido atualizada nos computadores cliente. Embora a Política de Grupo seja atualizada periodicamente sozinha, você pode forçar uma atualização imediata executando o comando a seguir em cada computador em que for necessário atualizar a Política de Grupo:

    Gpupdate.exe /force

Este comando pode ser executado em qualquer janela de comando que esteja sendo executada sob as credenciais de administrador. Para executar uma janela de comando sob credenciais de administrador, clique em **Iniciar**, clique com o botão direito em **Prompt de Comando** e clique em **Executar como administrador**.

Tenha em mente que essas políticas devem ser direcionadas para os computadores clientes. Eles não devem ser aplicados aos servidores que executam o Skype for Business Server.

Para ajudar a garantir que os pacotes de rede sejam marcados com o valore DSCP correto, você também deve criar uma nova entrada de registro em cada computador, concluindo o procedimento a seguir:

1.  Clique em **Iniciar** e, em seguida, em **Executar**.

2.  Na caixa de diálogo **executar** , digite **regedit**e pressione Enter.

3.  No editor do registro, expanda **\_hKey\_local Machine**, expanda **System**, expanda **CurrentControlSet**, expanda **Services**e, em seguida, expanda **tcpip**.

4.  Clique com o botão direito em **Tcpip**, aponte para **Novo** e clique em **Chave**. Após a criação da nova chave de registro, digite **QoS**e pressione ENTER para renomear a chave.

5.  Clique com o botão direito em **QoS**, aponte para **Novo** e clique em **Valor da Sequência**. Depois que o novo valor do registro for criado, tipo não **use NLA**e pressione ENTER para renomear o valor.

6.  Clique duas vezes em **não usar NLA**. Na caixa de diálogo **Editar Cadeia de caracteres** , digite **1** na caixa **dados de valor** e clique em **OK**.

7.  Feche o editor do registro e eboot seu computador.

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a>Configurar a qualidade do serviço em computadores com vários adaptadores de rede

Se você tiver um computador que tenha vários adaptadores de rede, você pode ocasionalmente executar em problemas nos quais os valores de DSCP são mostrados como 0x00, e não o valor configurado. Isso normalmente ocorre em computadores em que um ou mais adaptadores de rede não podem acessar seu domínio do Active Directory (por exemplo, se esses adaptadores são usados para uma rede privada). Em casos como esse, os valores de DSCP serão marcados para os adaptadores que podem acessar o domínio, mas não serão marcados para adaptadores que não podem acessar o domínio.

Se quiser marcar valores de DSCP para todos os adaptadores de rede em um computador, incluindo adaptadores que não têm acesso ao seu domínio, será necessário adicionar e configurar um valor ao registro. Isso pode ser feito realizando o procedimento a seguir:

1.  Clique em **Iniciar** e, em seguida, em **Executar**.

2.  Na caixa de diálogo **executar** , digite **regedit**e pressione Enter.

3.  No editor do registro, expanda **\_hKey\_local Machine**, expanda **System**, expanda **CurrentControlSet**, expanda **Services**e, em seguida, expanda **tcpip**.

4.  Se você não vir uma chave de registro identificada por **QoS** , clique com o botão direito em **tcpip**, aponte para **novo**e clique em **chave**. Após a criação da nova chave, digite **QoS**e pressione ENTER para renomear a chave.

5.  Clique com o botão direito em **QoS**, aponte para **Novo** e clique em **Valor da Sequência**. Depois que o novo valor do registro for criado, tipo não **use NLA**e pressione ENTER para renomear o valor.

6.  Clique duas vezes em **não usar NLA**. Na caixa de diálogo **Editar Cadeia de caracteres** , digite **1** na caixa **dados de valor** e clique em **OK**.

Após criar e configurar o novo valor do registro, será necessário reinicializar o computador para que as alterações entrem em vigor.

## <a name="see-also"></a>Confira também

[Criar um objeto de diretiva de grupo no Windows 10](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
