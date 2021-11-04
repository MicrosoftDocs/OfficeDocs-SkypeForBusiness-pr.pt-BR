---
title: Configurando intervalos de portas e uma Qualidade de Serviço para seus Servidores de Borda
ms.reviewer: ''
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
mtps_version: v=OCS.15
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Este artigo descreve como configurar intervalos de porta para Servidores de Borda e como configurar uma política de Qualidade de Serviço para seus Servidores de Borda A/V.
ms.openlocfilehash: 1f455ab417ed111a34134e3581806b4ce2a4bd57
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60778301"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-edge-servers-in-skype-for-business-server"></a>Configurando intervalos de porta e uma política de Qualidade de Serviço para seus Servidores de Borda em Skype for Business Server

Este artigo descreve como configurar intervalos de porta para Servidores de Borda e como configurar uma política de Qualidade de Serviço para seus Servidores de Borda A/V.

## <a name="configure-port-ranges"></a>Configurar intervalos de porta

Com servidores de Borda, você não precisa configurar intervalos de porta separados para compartilhamento de áudio, vídeo e aplicativos; Da mesma forma, os intervalos de porta usados para servidores de Borda não têm que corresponder aos intervalos de porta usados com seus servidores de Conferência, Aplicativo e Mediação. Antes de prosseguirmos com nosso exemplo, é importante enfatizar que, embora essa opção exista, recomendamos que você não altere os intervalos de porta, pois isso pode afetar adversamente alguns cenários se você sair do intervalo de porta 50000.

Por exemplo, suponha que você configurou seus servidores de Conferência, Aplicativo e Mediação para usar esses intervalos de porta:


<table>
<colgroup>
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


Como você pode ver, os intervalos de porta para áudio, vídeo e compartilhamento de aplicativos começam na porta 40803 e abrangem um total de 24732 portas. Se preferir, você pode configurar um determinado Servidor de Borda para usar esses valores gerais de porta executando um comando semelhante a este de dentro do Shell de Gerenciamento do Skype for Business Server:

  **Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730**

Ou use o comando a seguir para configurar simultaneamente todos os servidores de borda na organização:

  **Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_. Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}**

Você pode verificar as configurações de porta atuais para seus Servidores de Borda usando este comando Skype for Business Server Shell de Gerenciamento:

  **Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount**

Novamente, enquanto fornecemos essas opções, recomendamos que você deixe as coisas como estão para a configuração da porta.

## <a name="configure-a-qos-policy-for-your-av-edge-servers"></a>Configurar uma política de QoS para seus Servidores de Borda A/V

Além de criar políticas de QoS para seus servidores de Conferências, Aplicativos e Mediação, você também deve criar políticas de áudio e vídeo para o lado interno dos seus servidores de borda de A/V. No entanto, as políticas usadas em seus servidores de Borda são diferentes das políticas usadas em seus servidores de Conferências, Aplicativos e Mediação. Para os servidores de Conferência, Aplicativo e Mediação, você especificou um intervalo de porta de origem; com servidores de Borda, você precisa especificar um intervalo de portas de destino. Por isso, você não pode simplesmente aplicar as políticas QoS do servidor de Conferência, Aplicativo e Mediação aos servidores de Borda: essas políticas simplesmente não funcionarão. Em vez disso, você deve criar novas políticas e aplicá-las somente aos seus servidores de Borda.

O procedimento a seguir descreve o processo para criar objetos de Política de Grupo do Active Directory que podem ser usados para gerenciar a Qualidade de Serviço em Servidores de Borda. É possível, é claro, que seus servidores de Borda sejam servidores autônomos que não possuem contas do Active Directory. Neste caso, você pode usar uma Política de Grupo local em vez da Política de Grupo do Active Directory: a única diferença é que você deve criar essas políticas locais usando o Editor de Políticas de Grupo Local e deve criar individualmente o mesmo conjunto de políticas em cada Servidor de Borda. Para iniciar o Editor de Política de Grupo Local em um servidor de Borda, faça o seguinte:

1.  Clique em **Iniciar** e em **Executar**.

2.  Na caixa **de diálogo** Executar, digite **gpedit.msc** e pressione ENTER.

Se estiver criando políticas com base no Active Directory, você deve fazer logon em um computador em que o Gerenciamento de Política de Grupo tenha sido instalado. Nesse caso, abra o Gerenciamento de Política de Grupo (clique em **Iniciar**, aponte para Ferramentas Administrativas **e** clique em Gerenciamento de Política de **Grupo**) e conclua as seguintes etapas:

1.  No Gerenciamento de Política de Grupo, localize o contêiner em que a nova política deve ser criada. Por exemplo, se todos os seus computadores Skype for Business Server estão localizados em uma UO chamada Skype for Business Server, a nova política deve ser criada na UO Skype for Business Server.

2.  Clique com o botão direito do mouse no contêiner apropriado e clique em **Criar um GPO neste domínio e vincule-o aqui**.

3.  Na caixa de diálogo Novo **GPO,** digite um nome  para o novo objeto de Política de Grupo na caixa Nome (por exemplo, **Skype for Business Server Áudio**) e clique em **OK**.

4.  Clique com o botão direito do mouse na política recém-criada e clique em **Editar**.

A partir daqui o processo é idêntico, independente de você estar criando uma política do Active Directory ou uma política local:

1.  No Editor do Gerenciamento de Política de Grupo ou no Editor de Política de Grupo Local, expanda **Configuração do Computador**, **Políticas**, **Configurações do Windows**, clique com o botão direito em **QoS baseada em política** e clique em **Criar nova política**.

2.  Na caixa **de diálogo QoS** baseada em política, na página de abertura, digite um nome para a nova política (por exemplo, **Skype for Business Server Áudio**) na caixa **Nome.** Selecione **Especificar valor de DSCP** e defina o valor como **46**. Deixe a opção **Especificar Taxa de Aceleração de Saída** desmarcada e clique em **Avançar**.

3.  Na próxima página, certifique-se de que **Todos os aplicativos** estão selecionados e clique em **Próximo**. Esta configuração instrui a rede a procurar todos os pacotes com uma marcação de DSCP igual a 46, não somente pacotes criados por um aplicativo específico.

4.  Na terceira página, certifique-se de que qualquer endereço **IP** de origem e qualquer endereço **IP** de destino estão selecionados e clique em **Próximo**. Essas duas configurações garantem que os pacotes serão gerenciados independente de qual computador (endereço IP) tenha os enviado e de qual computador (endereço IP) os receberá.

5.  Na página quatro, selecione **TCP e UDP** na lista suspensa **Selecione o protocolo ao qual esta política de QoS se aplica**. TCP (Protocolo de Controle de Transmissão) e UDP (User Datagram Protocol) são os dois protocolos de rede mais usados pelo Skype for Business Server e seus aplicativos cliente.

6.  Sob o cabeçalho **Especifique o número da porta de destino**, selecione **A partir desta porta de destino ou intervalo**. Na caixa de texto que acompanha, digite o intervalo de portas reservado para transmissões de áudio. Por exemplo, se você reservou as portas 49152 por meio das portas 57500 para tráfego de áudio, insira o intervalo de portas usando esse formato: **49152:57500**. Clique em **Concluir**.

Depois de criar a política QoS para tráfego de áudio, você deve criar uma segunda política para tráfego de vídeo. Para criar uma política para vídeo, siga o mesmo procedimento básico da criação da política de áudio, fazendo as seguintes substituições:

  - Use um nome de política diferente (e exclusivo) (por exemplo, **Skype for Business Server Vídeo**).

  - Defina o valor do DSCP como **34** em vez de 46 (observe que você não precisa usar o valor 34 para o DSCP. O único requisito é usar para o vídeo um valor de DSCP diferente do valor usado para o áudio).

  - Use o intervalo de portas configurado anteriormente para tráfego de vídeo. Por exemplo, se você tiver reservado as portas 57501 a 65535 para vídeo, de definir o intervalo de portas como este: **57501:65535**. Novamente, isso deve ser configurado como intervalo de portas de destino.

Se você decidir criar uma política para gerenciar o tráfego de compartilhamento de aplicativos, deverá criar uma terceira política, fazendo as seguintes substituições:

  - Use um nome de política diferente (e exclusivo) (por exemplo, **Skype for Business Server Compartilhamento de Aplicativo).**

  - Defina o valor do DSCP como **24** em vez de 46 (novamente, não é necessário usar o valor 24 para o DSCP. O único requisito é usar para o compartilhamento de aplicativos um valor de DSCP diferente do valor usado para áudio e vídeo).

  - Use o intervalo de portas configurado anteriormente para tráfego de vídeo. Por exemplo, se você tiver reservado as portas 40803 a 49151 para compartilhamento de aplicativos, de definir o intervalo de portas como este: **40803:49151**.

As novas políticas criadas não terão efeito até que a Política de Grupo tenha sido atualizada nos servidores de Borda. Embora a Política de Grupo seja atualizada periodicamente sozinha, você pode forçar uma atualização imediata executando o comando a seguir em cada computador em que for necessário atualizar a Política de Grupo:

 **Gpudate.exe /force**

Esse comando pode ser executado de dentro do Skype for Business Server ou de qualquer janela de comando que está sendo executado sob credenciais de administrador. Para executar uma janela de comando sob credenciais de administrador, clique em **Iniciar**, clique com o botão direito em **Prompt de Comando** e clique em **Executar como administrador**. Observe que pode ser necessário reiniciar o servidor de Borda mesmo depois de executar o arquivo Gpudate.exe.

Para ajudar a garantir que os pacotes de rede sejam marcados com o valore DSCP correto, você também deve criar uma nova entrada de registro em cada computador, concluindo o procedimento a seguir:

1.  Clique em **Iniciar** e em **Executar**.

2.  Na caixa **de diálogo** Executar, digite **regedit** e pressione ENTER.

3.  No Editor do Registro, **expanda HKEY \_ LOCAL \_ MACHINE,** **expanda SYSTEM,** **expanda CurrentControlSet,** expanda **serviços** e **expanda Tcpip**.

4.  Clique com o botão direito em **Tcpip**, aponte para **Novo** e clique em **Chave**. Depois que a nova chave do Registro for criada, digite **QoS** e pressione ENTER para renomear a chave.

5.  Clique com o botão direito em **QoS**, aponte para **Novo** e clique em **Valor da Sequência**. Depois que o novo valor do Registro for criado, digite **Não usar NLA** e pressione ENTER para renomear o valor.

6.  Dê um duplo clique em **Não usar NLA**. Na caixa **de diálogo Editar Cadeia** de Caracteres, digite **1** na caixa **Dados Valor** e clique em **OK**.

7.  Feche o Editor do Registro e reinicie o computador.
