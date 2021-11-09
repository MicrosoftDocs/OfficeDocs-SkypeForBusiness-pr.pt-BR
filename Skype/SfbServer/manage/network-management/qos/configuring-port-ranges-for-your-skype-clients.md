---
title: Configurando intervalos de porta e uma política de Qualidade de Serviço para seus clientes
ms.reviewer: ''
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
mtps_version: v=OCS.15
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Este artigo descreve como configurar intervalos de porta para seus clientes e configurar políticas de Qualidade de Serviço no Skype for Business Server para clientes em execução em Windows 10.
ms.openlocfilehash: 5fa7a425bbb734307b487f63aa7fdf809f627661
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60860068"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a>Configurando intervalos de porta e uma política de Qualidade de Serviço para seus clientes em Skype for Business Server

Este artigo descreve como configurar intervalos de porta para seus clientes e configurar políticas de Qualidade de Serviço no Skype for Business Server para clientes em execução em Windows 10.

## <a name="configure-port-ranges"></a>Configurar intervalos de porta

Por padrão, Skype for Business aplicativos cliente podem usar qualquer porta entre as portas 1024 e 65535 quando envolvidos em uma sessão de comunicação; isso acontece porque intervalos de porta específicos não são habilitados automaticamente para clientes. Para poder usar a Qualidade do Serviço, no entanto, você precisará reatribuir os vários tipos de tráfego (áudio, vídeo, mídia, compartilhamento de aplicativos e transferência de arquivos) para uma série de intervalos de porta únicos. Isto pode ser realizado usando o cmdlet Set-CsConferencingConfiguration.

> [!NOTE]  
> Os usuários finais não podem fazer essas alterações por conta própria. As alterações de porta só podem ser feitas pelos administradores usando o cmdlet Set-CsConferencingConfiguration.


Você pode determinar quais intervalos de porta são usados atualmente para sessões de comunicação executando o seguinte comando no Shell de Gerenciamento Skype for Business Server:

**Get-CsConferencingConfiguration**

Supondo que você não tenha feito alterações nas configurações de conferência desde que instalou o Skype for Business Server, você deve obter informações de volta que incluam esses valores de propriedade:

ClientMediaPortRangeEnabled : False<br/>
ClientAudioPort : 5350<br/>
ClientAudioPortRange : 40<br/>
ClientVideoPort : 5350<br/>
ClientVideoPortRange : 40<br/>
ClientAppSharingPort : 5350<br/>
ClientAppSharingPortRange : 40<br/>
ClientFileTransferPort : 5350<br/>
ClientTransferPortRange : 40<br/>

Se você verificar o resultado anterior, você verá duas coisas de importância. Primeiro, a propriedade ClientMediaPortRangeEnabled é definida para False:

**ClientMediaPortRangeEnabled : False**

Isso é importante porque, quando essa propriedade for definida como False, os clientes Skype for Business usarão qualquer porta disponível entre as portas 1024 e 65535 quando envolvidos em uma sessão de comunicação; isso é verdadeiro independentemente de qualquer outra configuração de porta (por exemplo, ClientMediaPort ou ClientVideoPort). Se você deseja restringir o uso a um conjunto especificado de portas (e isso é algo que você deseja fazer se planeja implementar a Qualidade de Serviço), primeiro você deve habilitar intervalos de porta de mídia do cliente. Isso pode ser feito usando o seguinte comando Windows PowerShell:

**Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True**

O comando anterior habilita os intervalos de porta de mídia do cliente para o conjunto global de definições de configuração de conferência; no entanto, estas configurações também podem ser aplicadas para o escopo local e/ou de serviço (apenas para o serviço do Servidor de Conferência). Para habilitar os intervalos de porta de mídia do cliente para um site ou servidor específico, defina a Identidade deste site ou servidor ao chamar Set-CsConferencingConfiguration:

**Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True**

Em alternativa, é possível usar este comando para habilitar simultaneamente intervalos de portas para todas as suas definições de configuração de conferência:

**Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True**

A segunda coisa importante que você observará é o resultado de amostra mostrando que, por padrão, o conjunto de intervalos da porta de mídia para cada tipo de tráfego de rede são idênticos:

ClientAudioPort : 5350<br/>
ClientVideoPort : 5350<br/>
ClientAppSharingPort : 5350<br/>
ClientFileTransferPort : 5350<br/>

Para poder implementar o QoS, cada um destes intervalos de porta precisarão ser exclusivos. Por exemplo, você pode configurar os intervalos de porta desta forma:


<table>
<colgroup>
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
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>Vídeo</p></td>
<td><p>58000</p></td>
<td><p>20</p></td>
</tr>
<tr class="odd">
<td><p>Compartilhamento de aplicativo</p></td>
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


Na tabela anterior, os intervalos da porta do cliente representam um subconjunto dos intervalos de porta configurados para seus servidores. Por exemplo, nos servidores, o compartilhamento de aplicativos foi configurado para usar as portas 40803 a 49151; nos computadores clientes, o compartilhamento de aplicativos é configurado para usar as portas 42000 a 42019. Isso também é feito principalmente para facilitar a administração de QoS: as portas do cliente não têm que representar um subconjunto das portas usadas no servidor. (Por exemplo, nos computadores cliente, você pode configurar o compartilhamento de aplicativos para usar, por exemplo, portas 10000 a 10019.) No entanto, é recomendável que você faça dos intervalos de porta do cliente um subconjunto dos intervalos de porta do servidor.

Além disso, você pode ter percebido que 8348 portas foram reservados para compartilhamento de aplicativos nos servidores, mas apenas 20 portas foram deixadas de lado para compartilhamento de aplicativos nos clientes. Isso também é recomendado, mas não é uma regra dura e rápida. Em geral, você pode considerar cada porta disponível para representar uma única sessão de comunicação: se você tiver 100 portas disponíveis em um intervalo de portas, isso significa que o computador em questão poderia participar, no máximo, de 100 sessões de comunicação a qualquer momento. Como os servidores provavelmente participarão de muito mais conversas do que clientes, faz sentido abrir muito mais portas em servidores do que em clientes. A configuração de 20 portas para compartilhamento de aplicativos em um cliente significa que um usuário pode participar de 20 sessões de compartilhamento de aplicativos no dispositivo especificado e todas ao mesmo tempo. Isso deve ser suficiente para a grande maioria dos usuários.

Para atribuir os intervalos de porta anteriores à sua coleção global de configurações de conferência, você pode usar o seguinte comando Skype for Business Server Shell de Gerenciamento:

**Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 200**

Em alternativa, use este comando para atribuir estes mesmos intervalos de porta para todas suas definições de configuração de conferência:

**Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20**

Os usuários individuais devem fazer logoff Skype for Business e fazer logoff novamente antes que essas alterações realmente entre em vigor.

> [!NOTE]  
> Também é possível habilitar intervalos de porta da mídia do cliente e atribuir estes intervalos de porta usando um único comando. Por exemplo:<BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a>Configurar políticas de Qualidade de Serviço para clientes em execução em Windows 10

Além de especificar intervalos de porta para uso por seus clientes Skype for Business, você também deve criar políticas de Qualidade de Serviço separadas que serão aplicadas aos computadores cliente. (As políticas de Qualidade de Serviço criadas para servidores de Conferência, Aplicativo e Mediação não devem ser aplicadas a computadores cliente.) Essas informações se aplica somente a computadores que executam o cliente Skype for Business e Windows 10.

O exemplo a seguir usa esse conjunto de intervalos de porta para criar uma política de áudio e uma política de vídeo:


<table>
<colgroup>
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
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>Vídeo</p></td>
<td><p>58000</p></td>
<td><p>20</p></td>
</tr>
<tr class="odd">
<td><p>Compartilhamento de aplicativo</p></td>
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

Para criar uma política de áudio qualidade de serviço para computadores Windows 10, primeiro faça logoff em um computador onde o Gerenciamento de Política de Grupo foi instalado. Abra o Gerenciamento de Política de Grupo (clique em **Iniciar**, aponte para Ferramentas Administrativas **e** clique em Gerenciamento de Política de **Grupo**) e conclua o seguinte procedimento:

1.  No Gerenciamento de Política de Grupo, localize o contêiner em que a nova política deve ser criada. Por exemplo, se todos os seus computadores clientes estão localizados em uma UO denominada Clients, a nova política deve ser criada na UO cliente.

2.  Clique com o botão direito do mouse no contêiner apropriado e clique em **Criar um GPO neste domínio e vincule-o aqui**.

3.  Na caixa de diálogo Novo **GPO,** digite um nome para o novo objeto de Política de Grupo na caixa **Nome** e clique em **OK**.

4.  Clique com o botão direito do mouse na política recém-criada e clique em **Editar**.

5.  No Editor de Gerenciamento de Política de Grupo, **expanda** Configuração do Computador, expanda Windows Configurações **,** clique com o botão direito do mouse em **QoS** baseado em Política e clique em **Criar nova política**.

6.  Na caixa **de diálogo QoS** baseada em política, na página de abertura, digite um nome para a nova política na **caixa** Nome. Selecione **Especificar valor de DSCP** e defina o valor como **46**. Deixe a opção **Especificar Taxa de Aceleração de Saída** desmarcada e clique em **Avançar**.

7.  Na próxima página, selecione **Somente aplicativos** com  esse nome executável, digiteLync.execomo o nome e clique em **Próximo**. Essa configuração instrui a política a priorizar apenas o tráfego correspondente do Skype for Business cliente.

8.  Na terceira página, certifique-se de que qualquer endereço **IP** de origem e qualquer endereço **IP** de destino estão selecionados e clique em **Próximo**. Essas duas configurações garantem que os pacotes serão gerenciados independente de qual computador (endereço IP) tenha os enviado e de qual computador (endereço IP) os receberá.

9.  Na página quatro, selecione **TCP e UDP** na lista suspensa **Selecione o protocolo ao qual esta política de QoS se aplica**. TCP (Protocolo de Controle de Transmissão) e UDP (User Datagram Protocol) são os dois protocolos de rede mais usados pelo Skype for Business Server e seus aplicativos cliente.

10. No cabeçalho **Especifique o número da porta de origem**, selecione **Desta porta ou intervalo de origem**. Na caixa de texto acompanhante, digite o intervalo de porta reservado para transmissões de áudio. Por exemplo, se você reservou as portas 50020 até as portas 50039 para tráfego de áudio, insira o intervalo de portas usando esse formato: **50020:50039**. Clique em **Concluir**.

Depois de criar a política QoS para áudio, crie uma segunda política para vídeo. Para criar uma política para vídeo, siga o mesmo procedimento básico da criação da política de áudio, fazendo as seguintes substituições:

  - Use um nome de política diferente (e exclusivo).

  - Defina o valor DSCP para **34** em vez de 46. (Conforme mencionado anteriormente, você não precisa usar o valor DSCP 34; você simplesmente deve atribuir um valor DSCP diferente do usado para áudio.)

  - Use o intervalo de portas configurado anteriormente para tráfego de vídeo. Por exemplo, se você tiver reservado as portas 58000 a 58019 para vídeo, de definir o intervalo de portas como este: **58000:58019**.

Se você decidir criar uma política para gerenciar o tráfego de compartilhamento de aplicativos, faça estas substituições:

  - Use um nome de política diferente (e exclusivo) (por exemplo, **Skype for Business Server Compartilhamento de Aplicativo).**

  - Defina o valor DSCP para **24** em vez de 46. (Novamente, esse valor não precisa ser 24; ele simplesmente deve ser diferente dos valores DSCP usados para áudio e vídeo.)

  - Use o intervalo de portas configurado anteriormente para tráfego de vídeo. Por exemplo, se você reservou as portas 42000 a 42019 para compartilhamento de aplicativos, de definir o intervalo de portas para este: **42000:42019**.

Para uma política de transferência de arquivos:

  - Use um nome de política diferente (e exclusivo) (por exemplo, **Skype for Business Server Transferências de Arquivo**).

  - De definir o valor DSCP como **14**. (Novamente, esse valor não precisa ser 14; ele simplesmente deve ser um código DSCP exclusivo.)

  - Use o intervalo de portas configurado anteriormente para o aplicativo. Por exemplo, se você reservou as portas 42020 a 42039 para compartilhamento de aplicativos, de definir o intervalo de portas como este: **42020:42039**.

As novas políticas criadas não terão efeito até que a Política de Grupo seja atualizada em seus computadores clientes. Embora a Política de Grupo seja atualizada periodicamente sozinha, você pode forçar uma atualização imediata executando o comando a seguir em cada computador em que for necessário atualizar a Política de Grupo:

**Gpupdate.exe /force**

Esse comando pode ser executado em qualquer janela de comando que está sendo executado sob credenciais de administrador. Para executar uma janela de comando sob credenciais de administrador, clique em **Iniciar**, clique com o botão direito em **Prompt de Comando** e clique em **Executar como administrador**.

Lembre-se de que essas políticas devem ser direcionadas para seus computadores clientes. Eles não devem ser aplicados a servidores que executam Skype for Business Server.

Para ajudar a garantir que os pacotes de rede sejam marcados com o valore DSCP correto, você também deve criar uma nova entrada de registro em cada computador, concluindo o procedimento a seguir:

1.  Clique em **Iniciar** e em **Executar**.

2.  Na caixa **de diálogo** Executar, digite **regedit** e pressione ENTER.

3.  No Editor do Registro, **expanda HKEY \_ LOCAL \_ MACHINE,** **expanda SYSTEM,** **expanda CurrentControlSet,** expanda **serviços** e **expanda Tcpip**.

4.  Clique com o botão direito em **Tcpip**, aponte para **Novo** e clique em **Chave**. Depois que a nova chave do Registro for criada, digite **QoS** e pressione ENTER para renomear a chave.

5.  Clique com o botão direito em **QoS**, aponte para **Novo** e clique em **Valor da Sequência**. Depois que o novo valor do Registro for criado, digite **Não usar NLA** e pressione ENTER para renomear o valor.

6.  Clique duas **vezes em Não usar NLA**. Na caixa **de diálogo Editar Cadeia** de Caracteres, digite **1** na caixa **Dados Valor** e clique em **OK**.

7.  Feche o Editor do Registro e eboot seu computador.

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a>Configurar a Qualidade do Serviço em computadores com vários adaptadores de rede

Se você tiver um computador com vários adaptadores de rede, poderá ocasionalmente executar problemas em que os valores DSCP são mostrados como 0x00 em vez do valor configurado. Isso normalmente ocorrerá em computadores em que um ou mais adaptadores de rede não são capazes de acessar seu domínio do Active Directory (por exemplo, se esses adaptadores são usados para uma rede privada). Em casos como esse, os valores DSCP serão marcados para os adaptadores que podem acessar o domínio, mas não serão marcados para adaptadores que não podem acessar o domínio.

Se você quiser marcar valores DSCP para todos os adaptadores de rede em um computador, incluindo adaptadores que não têm acesso ao seu domínio, você precisará adicionar e configurar um valor ao Registro. Isso pode ser feito realizando o procedimento a seguir:

1.  Clique em **Iniciar** e em **Executar**.

2.  Na caixa **de diálogo** Executar, digite **regedit** e pressione ENTER.

3.  No Editor do Registro, **expanda HKEY \_ LOCAL \_ MACHINE,** **expanda SYSTEM,** **expanda CurrentControlSet,** expanda **serviços** e **expanda Tcpip**.

4.  Se você não vir uma chave do Registro rotulada **QoS,** clique com o botão direito do mouse em **Tcpip**, aponte para **Novo** e clique em **Tecla**. Depois que a nova chave for criada, digite **QoS** e pressione ENTER para renomear a chave.

5.  Clique com o botão direito em **QoS**, aponte para **Novo** e clique em **Valor da Sequência**. Depois que o novo valor do Registro for criado, digite **Não usar NLA** e pressione ENTER para renomear o valor.

6.  Clique duas **vezes em Não usar NLA**. Na caixa **de diálogo Editar Cadeia** de Caracteres, digite **1** na caixa **Dados Valor** e clique em **OK**.

Depois de criar e configurar o novo valor do Registro, você precisará reiniciar o computador para que as alterações entre em vigor.

## <a name="see-also"></a>Confira também

[Criar um objeto de política de grupo no Windows 10](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
