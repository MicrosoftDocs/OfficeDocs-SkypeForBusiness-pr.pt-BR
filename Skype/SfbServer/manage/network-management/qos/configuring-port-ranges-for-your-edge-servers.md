---
title: Configurando intervalos de porta e uma qualidade de serviço para seus servidores de borda
ms.reviewer: ''
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Este artigo descreve como configurar intervalos de portas para servidores de borda e como configurar uma política de qualidade de serviço para o seu A / V servidores de borda.
ms.openlocfilehash: 38fb71f995b1e4569b1bae11cc809ff0c5b358cc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33913073"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-edge-servers-in-skype-for-business-server"></a>Configurando intervalos de porta e uma política de qualidade de serviço para os servidores de borda em Skype para Business Server

Este artigo descreve como configurar intervalos de portas para servidores de borda e como configurar uma política de qualidade de serviço para o seu A / V servidores de borda.

## <a name="configure-port-ranges"></a>Configurar intervalos de porta

Com os servidores de borda, você não precisa configurar intervalos de portas separadas para áudio, vídeo e compartilhamento de aplicativos; da mesma forma, os intervalos de porta usados para servidores de borda não possuem que corresponder os intervalos de porta usados com os servidores de mediação, aplicativo e conferência. Antes de continuar com o nosso exemplo, é importante enfatizar que embora exista a essa opção, é recomendável que você não altere os intervalos de porta, pois isso pode afetar adversamente o alguns cenários se você mover fora do intervalo de 50000 portas.

Por exemplo, suponha que você configurou os servidores de mediação, aplicativo e conferência para usar esses intervalos de portas:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de pacote</th>
<th>Porta inicial</th>
<th>Número de portas reservadas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Compartilhamento de aplicativos</p></td>
<td><p>40803</p></td>
<td><p>8348</p></td>
</tr>
<tr class="even">
<td><p>Áudio</p></td>
<td><p>49152</p></td>
<td><p>8348</p></td>
</tr>
<tr class="odd">
<td><p>Vídeo</p></td>
<td><p>57500</p></td>
<td><p>8034</p></td>
</tr>
<tr class="even">
<td><p><strong>Totais</strong></p></td>
<td><p>--</p></td>
<td><p>24730</p></td>
</tr>
</tbody>
</table>


Como você pode ver, seus intervalos de porta para áudio, vídeo e iniciar na porta 40803 de compartilhamento de aplicativos e abranger um total de 24732 portas. Se você preferir, você pode configurar um determinado servidor de borda para usar estes valores de porta geral, executando um comando semelhante a este de dentro do Skype do Shell de gerenciamento do servidor de negócios:

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

Ou, use o seguinte comando para configurar simultaneamente todos os servidores de borda em sua organização:

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

Você pode verificar as configurações de porta atuais dos servidores de borda usando este Skype para o comando do Shell de gerenciamento do servidor de negócios:

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

Novamente, enquanto que fornecermos essas opções, é altamente recomendável que deixar as coisas como são para a configuração de porta.

## <a name="configure-a-qos-policy-for-your-av-edge-servers"></a>Configurar uma política de QoS para o seu A / V servidores de borda

Além de criar políticas de QoS para os servidores de mediação, aplicativo e conferência, você também deve criar políticas de áudio e vídeos para o lado interno do seu / servidores de borda V. No entanto, as diretivas usadas nos servidores de borda são diferentes de diretivas usadas em seus servidores de mediação, aplicativo e conferência. Para os servidores de mediação, aplicativo e conferência, você especificou um intervalo de porta de origem; com os servidores de borda, você precisa especificar um intervalo de porta de destino. Dessa forma, você simplesmente não é possível aplicar as diretivas de QoS de servidor de mediação, aplicativo e conferência para os servidores de borda: essas políticas simplesmente não funcionarão. Em vez disso, você deve criar novas políticas e aplicar essas políticas para os servidores de borda.

O procedimento a seguir descreve o processo de criação de objetos de diretiva de grupo do Active Directory que podem ser usados para gerenciar o Quality of Service nos servidores de borda. Obviamente, é possível que os servidores de borda são servidores autônomos que não têm contas do Active Directory. Se for esse o caso, você pode usar a diretiva de grupo local, em vez de diretiva de grupo do Active Directory: a única diferença é que você deve criar essas diretivas locais usando o Editor de diretiva de Grupo Local e individualmente deve criar o mesmo conjunto de políticas em cada servidor de borda. Para iniciar o Editor de diretiva de Grupo Local em um servidor de borda, faça o seguinte:

1.  Clique em  **Iniciar ** e em  **Executar **.

2.  Na caixa de diálogo **Executar** , digite **gpedit. msc**e pressione ENTER.

Se você estiver criando diretivas baseadas no Active Directory, em seguida, você deve fazer logon em um computador no qual o gerenciamento de diretiva de grupo tenha sido instalado. Nesse caso, abra o gerenciamento de diretiva de grupo (clique em **Iniciar**, aponte para **Ferramentas administrativas**e clique em **Gerenciamento de diretiva de grupo**) e, em seguida, conclua as seguintes etapas:

1.  Em gerenciamento de diretiva de grupo, localize o contêiner onde a nova diretiva deve ser criada. Por exemplo, se todos os seu Skype para computadores Business Server estiverem localizado em uma unidade Organizacional denominada Skype para Business Server, a nova diretiva deve ser criada no Skype para negócios UO de servidor.

2.  Com o botão direito do contêiner apropriado e clique em **criar um GPO neste domínio e vinculá-lo aqui**.

3.  Na caixa de diálogo **Novo GPO** , digite um nome para o novo objeto de diretiva de grupo na caixa **nome** (por exemplo, **Skype para o áudio do servidor de negócios**) e clique em **Okey**.

4.  Com o botão direito na política recém criada e clique em **Editar**.

A partir daqui o processo é idêntico, independente se você estiver criando uma política do Active Directory ou uma política local:

1.  No Editor de gerenciamento de diretiva de grupo ou o Editor de diretiva de Grupo Local, expanda **Configuração do computador**, expanda **diretivas**, expanda **Configurações do Windows**, do mouse em **QoS baseada em política**e clique em **Criar nova política**.

2.  Na caixa de diálogo **QoS baseada em política** , na página de abertura, digite um nome para a nova política (por exemplo, **Skype para o áudio do servidor de negócios**) na caixa **nome** . Selecione **Especificar valor de DSCP** e defina o valor para **46**. Deixe **Especificar taxa de aceleração saída** desmarcada e clique em **Avançar**.

3.  Na próxima página, certifique-se de que **todos os aplicativos** está selecionada e clique em **Avançar**. Essa configuração instrui a rede para procurar todos os pacotes com uma marcação de DSCP 46, não apenas de pacotes criados por um aplicativo específico.

4.  Na terceira página, certifique-se de que **qualquer endereço IP de origem** e de **qualquer endereço IP de destino** estão marcada e clique em **Avançar**. Estas duas configurações Certifique-se de que os pacotes serão gerenciados independentemente do computador (endereço IP) enviadas nesses pacotes e qual computador (endereço IP) receberá nesses pacotes.

5.  Na página quatro, selecione **TCP e UDP** na lista suspensa **, selecione o protocolo que essa política de QoS se aplica** . TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) são os dois protocolos de rede mais comumente usados pelo Skype para Business Server e seus aplicativos cliente.

6.  Sob o título, **Especifique o número da porta de destino**, selecione **este ou intervalo de porta de destino**. Na caixa de texto que o acompanha, digite o intervalo de portas reservado para transmissões de áudio. Por exemplo, se você reservadas portas 49152 através de portas 57500 para tráfego de áudio, insira o intervalo de portas usando este formato: **49152:57500**. Clique em **Concluir**.

Depois que você criou a política de QoS para o tráfego de áudio, você deve criar uma segunda política para o tráfego de vídeo. Para criar uma política para vídeo, siga o mesmo procedimento básico que seguiu quando criar a política de áudio, tornando essas substituições:

  - Use um nome de política diferente (e único) (por exemplo, **Skype para Business Server vídeo**).

  - Defina o valor DSCP para **34** , em vez de 46. (Observe que você não precisa usar um valor DSCP de 34. O único requisito é que você use um valor DSCP diferente para vídeo que você usou para áudio.)

  - Use o intervalo de portas previamente configurados para o tráfego de vídeo. Por exemplo, se você tiver reservadas portas 57501 a 65535 para vídeo, defina o intervalo de portas a esta: **57501:65535**. Novamente, isso deve ser configurado como o intervalo de porta de destino.

Se você decidir criar uma política para gerenciar o tráfego de compartilhamento de aplicativo, você deve criar uma terceira política, fazendo as seguintes substituições:

  - Use um nome de política diferente (e único) (por exemplo, **Skype para compartilhamento de aplicativos do Business Server**).

  - Defina o valor DSCP para **24** em vez de 46. (Novamente, você não precisará usar um valor DSCP de 24. O único requisito é que você use um valor DSCP diferente para compartilhamento de aplicativos que você usou para áudio ou vídeo.)

  - Use o intervalo de portas previamente configurados para o tráfego de vídeo. Por exemplo, se você tiver reservadas portas 40803 através de 49151 para compartilhamento de aplicativos, defina o intervalo de portas a esta: **40803:49151**.

As novas políticas que você criou não terão efeito até que a diretiva de grupo tenha sido atualizada nos servidores de borda. Embora a Política de Grupo seja periodicamente atualizada por si só, você pode forçar a atualização imediata executando o comando a seguir em cada computador em que a Política de Grupo deve ser atualizada:

    Gpudate.exe /force

Este comando pode ser executado de dentro do Skype para Business Server ou de qualquer janela de comando que está sendo executado em credenciais de administrador. Para executar uma janela de comando com credenciais de administrador, clique em **Iniciar**, clique com o botão direito do mouse em **Prompt de Comando** e clique em **Executar como administrador**. Observe que talvez seja necessário reiniciar o servidor de borda mesmo após executar Gpudate.exe.

Para ajudar a garantir que os pacotes de rede sejam marcados com o valor DSCP apropriado, você também deve criar uma nova entrada de registro em cada computador, Concluindo o seguinte procedimento:

1.  Clique em  **Iniciar ** e em  **Executar **.

2.  Na caixa de diálogo **Executar** , digite **regedit**e pressione ENTER.

3.  No Editor do registro, expanda **HKEY\_LOCAL\_máquina**, expanda **SYSTEM**, expanda **CurrentControlSet**, expanda **Serviços**e depois expanda **Tcpip**.

4.  Clique com o botão **Tcpip**, aponte para **novo**e clique em **chave**. Depois que a nova chave do registro é criada, digite **QoS**e pressione ENTER para renomear a chave.

5.  Com o botão direito **QoS**, aponte para **novo**e clique em **Valor de cadeia de caracteres**. Depois que o novo valor do registro é criado, digite **não use NLA**e pressione ENTER para renomear o valor.

6.  Clique duas vezes em **fazer sem uso NLA**. Na caixa de diálogo **Editar cadeia de caracteres** , digite **1** na caixa **dados do valor** e clique em **Okey**.

7.  Feche o Editor do registro e reinicie seu computador.
