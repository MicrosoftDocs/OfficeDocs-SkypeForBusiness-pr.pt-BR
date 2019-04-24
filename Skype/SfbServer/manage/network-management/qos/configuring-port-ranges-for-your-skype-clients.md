---
title: Configurando intervalos de porta e uma política de qualidade de serviço para seus clientes
ms.reviewer: ''
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Este artigo descreve como configurar intervalos de portas para seus clientes e configurando políticas de qualidade de serviço do Skype para Business Server para clientes executando o Windows 10.
ms.openlocfilehash: 2e5328406634302a1b076eec8466e7f7b9245150
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219720"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a>Configurando intervalos de porta e uma política de qualidade de serviço para os clientes do Skype para Business Server

Este artigo descreve como configurar intervalos de portas para seus clientes e configurando políticas de qualidade de serviço do Skype para Business Server para clientes executando o Windows 10.

## <a name="configure-port-ranges"></a>Configurar intervalos de porta

Por padrão, Skype para aplicativos de cliente de negócios podem usar qualquer porta entre portas 1024 e 65535 quando estiver envolvido em uma sessão de comunicação; Isso ocorre porque os intervalos de porta específica não são automaticamente habilitados para clientes. Para usar a qualidade de serviço, no entanto, você precisará reatribuir os vários tipos de tráfego (áudio, vídeo, mídia, compartilhamento de aplicativos e transferência de arquivos) a uma série de intervalos de porta exclusivo. Isso pode ser feito usando o cmdlet Set-CsConferencingConfiguration.

> [!NOTE]  
> Os usuários finais não pode fazer essas alterações em si. Alterações de porta só podem ser feitas por administradores usando o cmdlet Set-CsConferencingConfiguration.


Você pode determinar quais intervalos de porta são usados atualmente para sessões de comunicação executando o seguinte comando dentro do Skype do Shell de gerenciamento do servidor de negócios:

    Get-CsConferencingConfiguration

Supondo que não fazer qualquer alteração em suas configurações de conferência desde que instalou o Skype para Business Server, você deve obter informações que incluem estes valores de propriedade:

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

Se você observe atentamente a saída anterior, você verá duas coisas de importância. Em primeiro lugar, a propriedade ClientMediaPortRangeEnabled é definida como False:

    ClientMediaPortRangeEnabled : False

Isso é importante porque, quando essa propriedade é definida como False, Skype para clientes corporativos irá usar qualquer porta disponível entre portas 1024 e 65535 quando estiver envolvido em uma sessão de comunicação; Isso é verdadeiro independentemente de qualquer outra configuração de porta (por exemplo, ClientMediaPort ou ClientVideoPort). Se você deseja restringir o uso de um conjunto especificado de portas (e isso é algo que você deseja fazer se você planeja implementar Quality of Service), em seguida, você deve primeiro habilitar intervalos de portas de mídia do cliente. Que pode ser feito usando o seguinte comando do Windows PowerShell:

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

O comando anterior habilita os intervalos de portas de mídia do cliente para a coleção global de definições de configuração de conferência; No entanto, essas configurações também podem ser aplicadas ao escopo do site e/ou o escopo do serviço (apenas para o servidor de conferência serviço). Intervalos para um site específico ou um servidor da porta de mídia do cliente para permitir que especifique a identidade do site ou o servidor ao chamar Set-CsConferencingConfiguration:

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

Como alternativa, você pode usar este comando para habilitar simultaneamente intervalos de portas para todas as suas definições de configuração de conferência:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

A segunda coisa importante que você observará é que o resultado de amostra mostrando que, por padrão, as portas de mídia intervalos definido para cada tipo de tráfego de rede é idênticos:

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

Para implementar o QoS, cada um desses intervalos de portas precisará ser exclusivo. Por exemplo, você pode configurar os intervalos de porta semelhante a esta:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de tráfego do cliente</th>
<th>Porta de início</th>
<th>Intervalo de portas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Áudio</p></td>
<td><p>50020</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>Vídeo</p></td>
<td><p>58000</p></td>
<td><p>20</p></td>
</tr>
<tr class="odd">
<td><p>Compartilhamento de aplicativos</p></td>
<td><p>42000</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>Transferência de arquivos</p></td>
<td><p>42020</p></td>
<td><p>20</p></td>
</tr>
</tbody>
</table>


Na tabela anterior, os intervalos de porta do cliente representam um subconjunto dos intervalos de porta configurada para os seus servidores. Por exemplo, nos servidores, compartilhamento de aplicativos foi configurado para usar portas 40803 por meio de 49151; nos computadores cliente, compartilhamento de aplicativos é configurado para usar portas 42000 por meio de 42019. Isso, também, é feito principalmente para facilitar a administração de QoS: portas do cliente não precisa representam um subconjunto das portas usadas no servidor. (Por exemplo, nos computadores cliente você poderia configurar o compartilhamento de aplicativos para usar, digamos, portas 10000 através de 10019.) No entanto, é recomendável que você faça seu cliente de intervalos de porta um subconjunto dos intervalos de porta de servidor.

Além disso, você pode ter percebido que 8348 portas foram postas para compartilhamento nos servidores de aplicativos, mas apenas 20 portas foram postas para os clientes de compartilhamento de aplicativos. Isso, também, é recomendável, mas não for uma regra prontas. Em geral, você pode considerar cada porta disponível para representar uma sessão de comunicação único: se você tiver 100 portas disponíveis em um intervalo de porta, o que significa que o computador em questão pode participar, no máximo, 100 sessões de comunicação a qualquer momento. Porque os servidores provavelmente serão participar de várias conversas mais que clientes, faz sentido para abrir muitas portas nos servidores que nos clientes. Configuração aside 20 portas compartilhamento de aplicativo em um cliente significa que um usuário pode participar de sessões de compartilhamento de aplicativo 20 no dispositivo especificado e todos ao mesmo tempo. Que deve comprovar suficiente para a maioria dos usuários.

Para atribuir os intervalos de porta anteriores para seu conjunto global de definições de configuração de conferência, você pode usar a seguir Skype de comando do Shell de gerenciamento do servidor de negócios:

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

Ou, use este comando para atribuir estes mesmos intervalos de porta para todas as suas conferências definições de configuração:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

Usuários individuais devem fazer logoff do Skype para negócios e, em seguida, logon novamente antes que essas alterações realmente terem efeito.

> [!NOTE]  
> Você pode também habilitar intervalos de portas de mídia do cliente e, em seguida, atribuir esses intervalos de porta, usando um único comando. Por exemplo:<BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a>Configurar políticas de qualidade de serviço para clientes executando o Windows 10

Além de especificar intervalos de portas para uso pela sua Skype para clientes corporativos, você também deve criar diretivas de qualidade de serviço separadas que serão aplicadas aos computadores cliente. (As políticas de qualidade de serviço criadas para os servidores de mediação, aplicativo e conferência não devem ser aplicadas aos computadores cliente.) Essas informações só se aplica a computadores que executam o Skype para o cliente de negócios e Windows 10.

O exemplo a seguir usa este conjunto de intervalos de portas para criar uma política de áudio e uma política de vídeo:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de tráfego do cliente</th>
<th>Porta de início</th>
<th>Intervalo de portas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Áudio</p></td>
<td><p>50020</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>Vídeo</p></td>
<td><p>58000</p></td>
<td><p>20</p></td>
</tr>
<tr class="odd">
<td><p>Compartilhamento de aplicativos</p></td>
<td><p>42000</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>Transferência de arquivos</p></td>
<td><p>42020</p></td>
<td><p>20</p></td>
</tr>
</tbody>
</table>

Para criar uma política de áudio de qualidade de serviço para computadores Windows 10, primeiro faça logon em um computador no qual o gerenciamento de diretiva de grupo tenha sido instalado. Abra Gerenciamento de diretiva de grupo (clique em **Iniciar**, aponte para **Ferramentas administrativas**e clique em **Gerenciamento de diretiva de grupo**) e conclua o procedimento a seguir:

1.  Em gerenciamento de diretiva de grupo, localize o contêiner onde a nova diretiva deve ser criada. Por exemplo, se todos os computadores cliente estão localizados em uma unidade Organizacional denominada clientes, a nova diretiva deve ser criada na unidade Organizacional cliente.

2.  Com o botão direito do contêiner apropriado e clique em **criar um GPO neste domínio e vinculá-lo aqui**.

3.  Na caixa de diálogo **Novo GPO** , digite um nome para o novo objeto de diretiva de grupo na caixa **nome** e clique em **Okey**.

4.  Com o botão direito na política recém criada e clique em **Editar**.

5.  No Editor de gerenciamento de diretiva de grupo, expanda **Configuração do computador**, expanda **Configurações do Windows**, do mouse em **QoS baseada em política**e clique em **Criar nova política**.

6.  Na caixa de diálogo **QoS baseada em política** , na página de abertura, digite um nome para a nova política na caixa **nome** . Selecione **Especificar valor de DSCP** e defina o valor para **46**. Deixe **Especificar taxa de aceleração saída** desmarcada e clique em **Avançar**.

7.  Na próxima página, certifique-se de que **todos os aplicativos** está selecionada e clique em **Avançar**. Essa configuração instrui a rede para procurar todos os pacotes com uma marcação de DSCP 46, não apenas de pacotes criados por um aplicativo específico.

8.  Na terceira página, certifique-se de que **qualquer endereço IP de origem** e de **qualquer endereço IP de destino** estão marcada e clique em **Avançar**. Estas duas configurações Certifique-se de que os pacotes serão gerenciados independentemente do computador (endereço IP) enviadas nesses pacotes e qual computador (endereço IP) receberá nesses pacotes.

9.  Na página quatro, selecione **TCP e UDP** na lista suspensa **, selecione o protocolo que essa política de QoS se aplica** . TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) são os dois protocolos de rede mais comumente usados pelo Skype para Business Server e seus aplicativos cliente.

10. Sob o título, **Especifique o número da porta de origem**, selecione **este ou intervalo de porta de origem**. Na caixa de texto que o acompanha, digite o intervalo de portas reservado para transmissões de áudio. Por exemplo, se você reservada portas 50020 através de portas 50039 para tráfego de áudio insira o intervalo de portas usando este formato: **50020:50039**. Clique em **Concluir**.

Depois que você criou a política de QoS para áudio, em seguida, crie uma segunda política para vídeo. Para criar uma política para vídeo, siga o mesmo procedimento básico que seguiu quando criar a política de áudio, tornando essas substituições:

  - Use um nome de política diferente (e único).

  - Defina o valor DSCP para **34** , em vez de 46. (Conforme observado anteriormente, você não precisará usar o valor DSCP 34; você simplesmente deve atribuir um valor DSCP diferente daquela usada para áudio).

  - Use o intervalo de portas previamente configurados para o tráfego de vídeo. Por exemplo, se você tiver reservadas portas 58000 por meio de 58019 para vídeo, defina o intervalo de portas a esta: **58000:58019**.

Se você decidir criar uma política para gerenciar o tráfego de compartilhamento de aplicativos, faça essas substituições:

  - Use um nome de política diferente (e único) (por exemplo, **Skype para compartilhamento de aplicativos do Business Server**).

  - Defina o valor DSCP para **24** em vez de 46. (Novamente, este valor não precisam ser 24; ele simplesmente deve ser diferente do que os valores DSCP usados para áudio e vídeo).

  - Use o intervalo de portas previamente configurados para o tráfego de vídeo. Por exemplo, se você tiver reservadas portas 42000 através do 42019 para compartilhamento de aplicativos, defina o intervalo de portas a esta: **42000:42019**.

Para uma diretiva de transferência de arquivo:

  - Use um nome de política diferente (e único) (por exemplo, **Skype para transferências de arquivos do servidor de negócios**).

  - Defina o valor DSCP para **14**. (Novamente, este valor não precisam ser 14; ele simplesmente deve ser um código DSCP exclusivo).

  - Use o intervalo de portas previamente configurados para o aplicativo. Por exemplo, se você tiver reservadas portas 42020 através do 42039 para compartilhamento de aplicativos, defina o intervalo de portas a esta: **42020:42039**.

As novas políticas que você criou não terão efeito até que a diretiva de grupo tenha sido atualizada em seus computadores cliente. Embora a Política de Grupo seja periodicamente atualizada por si só, você pode forçar a atualização imediata executando o comando a seguir em cada computador em que a Política de Grupo deve ser atualizada:

    Gpudate.exe /force

Esse comando pode ser executado em qualquer janela de comando executada com credenciais de administrador. Para executar uma janela de comando com credenciais de administrador, clique em **Iniciar**, clique com o botão direito do mouse em **Prompt de Comando** e clique em **Executar como administrador**.

Tenha em mente que essas políticas devem ser voltadas para os seus computadores clientes. Não deve ser aplicadas aos servidores que executam o Skype para Business Server.

Para ajudar a garantir que os pacotes de rede sejam marcados com o valor DSCP apropriado, você também deve criar uma nova entrada de registro em cada computador, Concluindo o seguinte procedimento:

1.  Clique em  **Iniciar ** e em  **Executar **.

2.  Na caixa de diálogo **Executar** , digite **regedit**e pressione ENTER.

3.  No Editor do registro, expanda **HKEY\_LOCAL\_máquina**, expanda **SYSTEM**, expanda **CurrentControlSet**, expanda **Serviços**e depois expanda **Tcpip**.

4.  Clique com o botão **Tcpip**, aponte para **novo**e clique em **chave**. Depois que a nova chave do registro é criada, digite **QoS**e pressione ENTER para renomear a chave.

5.  Com o botão direito **QoS**, aponte para **novo**e clique em **Valor de cadeia de caracteres**. Depois que o novo valor do registro é criado, digite **não use NLA**e pressione ENTER para renomear o valor.

6.  Clique duas vezes em **não use NLA**. Na caixa de diálogo **Editar cadeia de caracteres** , digite **1** na caixa **dados do valor** e clique em **Okey**.

7.  Feche o Editor do registro e i:eboot seu computador.

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a>Configurar a qualidade de serviço em computadores com vários adaptadores de rede

Se você tiver um computador que tenha vários adaptadores de rede, você pode executar ocasionalmente problemas onde os valores DSCP são mostrados como 0x00 ao invés do valor configurado. Normalmente, isso ocorrerá nos computadores em que um ou mais dos adaptadores de rede não serão possível acessar o domínio do Active Directory (por exemplo, se esses adaptadores são usados para uma rede privada). Em casos assim, os valores DSCP serão marcados para os adaptadores que podem acessar o domínio, mas não serão marcados para adaptadores que não é possível acessar o domínio.

Se você gostaria de valores DSCP de marca para todos os adaptadores de rede em um computador, inclusive adaptadores que não têm acesso ao seu domínio, você precisará adicionar e configurar um valor no registro. Que pode ser feito, completando o procedimento a seguir:

1.  Clique em  **Iniciar ** e em  **Executar **.

2.  Na caixa de diálogo **Executar** , digite **regedit**e pressione ENTER.

3.  No Editor do registro, expanda **HKEY\_LOCAL\_máquina**, expanda **SYSTEM**, expanda **CurrentControlSet**, expanda **Serviços**e depois expanda **Tcpip**.

4.  Se você não vir uma chave de registro rotulada **QoS** , em seguida, clique com o botão **Tcpip**, aponte para **novo**e clique em **chave**. Depois que a nova chave é criada, digite **QoS**e pressione ENTER para renomear a chave.

5.  Com o botão direito **QoS**, aponte para **novo**e clique em **Valor de cadeia de caracteres**. Depois que o novo valor do registro é criado, digite **não use NLA**e pressione ENTER para renomear o valor.

6.  Clique duas vezes em **não use NLA**. Na caixa de diálogo **Editar cadeia de caracteres** , digite **1** na caixa **dados do valor** e clique em **Okey**.

Após criar e configurar o novo valor do registro, você precisará reiniciar o computador para que as alterações entrem em vigor.

## <a name="see-also"></a>Confira também

[Criar um objeto de diretiva de grupo no Windows 10](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
