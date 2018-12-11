---
title: Configurando intervalos de porta e uma política de qualidade de serviço para seus servidores de mediação, aplicativo e conferência
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Este artigo descreve como configurar intervalos de porta e uma política de qualidade de serviço para seus servidores de mediação, aplicativo e conferência.
ms.openlocfilehash: 736a0d343c67585266833195780c7f76cbee51dd
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27223434"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers"></a>Configurando intervalos de porta e uma política de qualidade de serviço para seus servidores de mediação, aplicativo e conferência

Este artigo descreve como configurar intervalos de porta e uma política de qualidade de serviço para seus servidores de mediação, aplicativo e conferência.

## <a name="configure-port-ranges"></a>Configurar intervalos de porta

Para implementar o Quality of Service, você deve configurar intervalos de porta idênticos para áudio, vídeo e compartilhamento em seus servidores de mediação, aplicativo e conferência; de aplicativos Além disso, esses intervalos de portas não devem ser sobrepostos de nenhuma maneira. Para usar um exemplo simples, vamos supor que você usa as portas 10000 por meio de 10999 para vídeo em seus servidores de conferência. Isso significa que você também deve reservar portas 10000 por meio de 10999 para vídeo em seus servidores de mediação e de aplicativo. Se você não fizer isso, QoS não funcionará conforme o esperado.

Da mesma forma, suponha que você reservar portas 10000 por meio de 10999 para vídeo, mas reserva portas 10500 por meio de 11999 para áudio. Isso pode criar problemas de qualidade de serviço, porque a sobreposição de intervalos de porta. Com o QoS, cada modalidade deve ter um conjunto exclusivo de portas: se você usar portas 10000 por meio de 10999 para vídeo, você terá que usar um intervalo diferente (por exemplo, 11000 por meio de 11999, para áudio).

Por padrão, os intervalos de porta de áudio e vídeo não se sobreponham no Skype para Business Server; No entanto, os intervalos de porta atribuída ao aplicativo de sobreposição de compartilhamento com ambos os intervalos de porta de áudio e vídeo. (Que, por sua vez, significa que nenhum desses intervalos são exclusivos.) Você pode verificar os intervalos de porta existente para os servidores de mediação, aplicativo e conferência, executando os seguintes três comandos de dentro do Skype do Shell de gerenciamento do servidor de negócios:

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

> [!WARNING]  
> Como você pode ver nos comandos anteriores, cada tipo de porta – áudio, vídeo e compartilhamento de aplicativos – é atribuído dois valores de propriedade separada: a porta de início e a contagem de porta. A porta de início indica a primeira porta usada para esse modalidade; Por exemplo, se o início da porta de áudio for igual a 50000 isso significa que a primeira porta usada para o tráfego de áudio é a porta 50000. Se a contagem de porta de áudio é 2 (que não é um valor válido, mas é usado aqui para fins ilustrativos), isso significa que apenas duas portas são alocadas para áudio. Se a primeira porta é a porta 50000 e há um total de duas portas, isso significa que a segunda porta deve ser a porta 50001 (porta intervalos precisam ser contíguos). Como resultado, o intervalo de portas para áudio seria portas 50000 por meio de 50001, inclusive.<BR><br>Observe também que o servidor de aplicativo e servidor de mediação apenas suportem a QoS para áudio; Você não precisará alterar vídeo ou portas em seus servidores de aplicativos ou servidores de mediação de compartilhamento de aplicativos.

Se você executar os três comandos anteriores, você verá que a porta padrão valores para Skype para Business Server configurados como esta:

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Propriedade</th>
<th>Servidor de conferência</th>
<th>Servidor de aplicativos</th>
<th>Servidor de Mediação</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AudioPortStart</p></td>
<td><p>49152</p></td>
<td><p>49152</p></td>
<td><p>49152</p></td>
</tr>
<tr class="even">
<td><p>AudioPortCount</p></td>
<td><p>8348</p></td>
<td><p>8348</p></td>
<td><p>8348</p></td>
</tr>
<tr class="odd">
<td><p>VideoPortStart</p></td>
<td><p>57501</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p>VideoPortCount</p></td>
<td><p>8034</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="odd">
<td><p>ApplicationSharingPortStart</p></td>
<td><p>49152</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p>ApplicationSharingPortCount</p></td>
<td><p>16383</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
</tbody>
</table>

Conforme observado anteriormente, ao configurar Skype para o servidor de negócios de portas para QoS, você deve assegurar que: 1) configurações de porta de áudio são idênticas em seus servidores de mediação, aplicativo e conferência; e, 2) intervalos de porta não se sobreponham. Se você observe atentamente a tabela anterior, você verá os intervalos de porta são idênticos entre os tipos de três servidores. Por exemplo, a porta de áudio inicial é definida para a porta 49152 em cada tipo de servidor e o número total de portas reservadas para áudio em cada servidor também é idêntico: 8348. No entanto, a porta intervalos sobreposição: início de portas de áudio na porta 49152, mas isso faça as portas reserve para compartilhamento de aplicativos. Para fazer uso eficaz do Quality of Service, o compartilhamento de aplicativos deve ser reconfigurado para usar um intervalo de porta exclusivo. Por exemplo, você poderia configurar para iniciar na porta 40803 e usar 8348 portas de compartilhamento de aplicativos. (Por que 8348 portas? Se você adicionar esses valores juntos-- 40803 + 8348 – que significa que a compartilhamento de aplicativos usar portas 40803 através da porta 49150. Porque as portas de áudio não começam até a porta 49152, você não terá mais qualquer sobrepostas intervalos de porta.)

Depois de ter selecionado o novo intervalo de porta para compartilhamento de aplicativos, você pode fazer as alterações usando o cmdlet Set-CsConferencingServer. Essa alteração não precisam ser feitas em seus servidores de aplicativo ou em seus servidores de mediação, pois esses servidores não manipular o tráfego de compartilhamento de aplicativo. Você precisará alterar os valores de porta nesses servidores se você decidir reatribuir as portas usadas para o tráfego de áudio.

Para modificar os valores de porta do compartilhamento de aplicativo em um único servidor de conferência, execute um comando semelhante a esse a partir dentro do Skype do Shell de gerenciamento do servidor de negócios:

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

Se você quiser fazer essas alterações em todos os servidores de conferência, você pode executar esse comando em vez disso:

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

Após alterar as configurações de porta, você deve parar e, em seguida, reiniciar cada serviço afetado pelas alterações.

Não é obrigatório que seus servidores de conferência, servidores de aplicativos e servidores de mediação compartilham o intervalo de portas mesmo exato; o requisito de true somente é que você reserve intervalos de porta exclusivo em todos os servidores. No entanto, a administração geralmente será mais fácil se você usar o mesmo conjunto de portas em todos os servidores.

## <a name="configure-a-quality-of-service-policy-in-skype-for-business-server-for-your-conferencing-application-and-mediation-servers"></a>Configurar uma política de qualidade de serviço no Skype para Business Server para os servidores de mediação, aplicativo e conferência

Configurando intervalos de portas facilita o uso de qualidade de serviço, garantindo que todo o tráfego de um tipo especificado (por exemplo, todo o tráfego áudio) passa pelo mesmo conjunto de portas. Isso facilita para o sistema identificar e marcar um determinado pacote: se a porta 49152 é reservada para o tráfego de áudio, então qualquer pacote viajando por porta 49152 pode ser marcado com um código DSCP que indica que este é um pacote de áudio. Por sua vez, isso permite que os roteadores identificar o pacote como um pacote de áudio e dê a ela uma prioridade maior que pacotes desmarcados (por exemplo, pacotes usados para copiar um arquivo de um servidor para outro).

No entanto, o restringir simplesmente um conjunto de portas para um tipo específico de tráfego não resultar em pacotes viajando através das portas que sejam marcadas com o código DSCP apropriado. Além de definir intervalos de porta, você também deve criar políticas de qualidade de serviço que especificam o código DSCP a ser associado a cada intervalo de portas. Para Skype para Business Server, que geralmente significa criando duas diretivas: uma para áudio e outra para vídeo.

Qualidade das diretivas de serviço são mais facilmente criado e gerenciado, usando a diretiva de grupo. (Essas políticas a mesmas também podem ser criadas usando diretivas de segurança local. No entanto, que requer a repita o mesmo procedimento em cada computador.) O conjunto inicial de políticas de QoS (um para áudio) e outro para vídeo deve ser aplicado apenas ao Skype para computadores Business Server executando o servidor de conferência, servidor de aplicativos e/ou os serviços de servidor de mediação. Se todos esses computadores estiverem localizados na mesma UO Active Directory, você pode simplesmente atribuir o novo objeto de diretiva de grupo (GPO) a essa UO. Como alternativa, você pode seguir outras etapas para direcionar a nova política aos computadores especificados; Por exemplo, você pode colocar os computadores adequados em um grupo de segurança e use a filtragem de segurança de diretiva de grupo para aplicar o GPO apenas a esse grupo de segurança.

Para criar uma política de qualidade de serviço de gerenciamento de áudio, faça logon em um computador no qual o gerenciamento de diretiva de grupo tenha sido instalado. Abra Gerenciamento de diretiva de grupo (clique em **Iniciar**, aponte para **Ferramentas administrativas**e clique em **Gerenciamento de diretiva de grupo**) e conclua o procedimento a seguir:

1.  Em gerenciamento de diretiva de grupo, localize o contêiner onde a nova diretiva deve ser criada. Por exemplo, se todos os seu Skype para computadores Business Server estiverem localizado em uma unidade Organizacional denominada Skype para Business Server, em seguida, a nova diretiva deve ser criada do Skype Business Server ou.

2.  Com o botão direito do contêiner apropriado e clique em **criar um GPO neste domínio e vinculá-lo aqui**.

3.  Na caixa de diálogo **Novo GPO** , digite um nome para o novo objeto de diretiva de grupo na caixa **nome** (por exemplo, **Skype para Business Server QoS**) e clique em **Okey**.

4.  Com o botão direito na política recém criada e clique em **Editar**.

5.  No Editor de gerenciamento de diretiva de grupo, expanda **Configuração do computador**, expanda **diretivas**, expanda **Configurações do Windows**, do mouse em **QoS baseada em política**e clique em **Criar nova política**.

6.  Na caixa de diálogo **QoS baseada em política** , na página de abertura, digite um nome para a nova política (por exemplo, **Skype para Business Server QoS**) na caixa **nome** . Selecione **Especificar valor de DSCP** e defina o valor para **46**. Deixe **Especificar taxa de aceleração saída** desmarcada e clique em **Avançar**.

7.  Na próxima página, certifique-se de que **todos os aplicativos** está selecionada e clique em **Avançar**. Isso simplesmente garante que todos os aplicativos corresponderá pacotes a partir do intervalo de portas especificado com o código DSCP especificado.

8.  Na terceira página, certifique-se de que ambas as **qualquer endereço IP de origem e qualquer endereço IP de destino** estão selecionadas e clique em **Avançar**. Estas duas configurações Certifique-se de que os pacotes serão gerenciados independentemente do computador (endereço IP) enviadas nesses pacotes e qual computador (endereço IP) receberá nesses pacotes.

9.  Na página quatro, selecione **TCP e UDP** na lista suspensa **, selecione o protocolo que essa política de QoS se aplica** . TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) são os dois protocolos de rede mais comumente usados pelo Skype para Business Server e seus aplicativos cliente.

10. Sob o título, **Especifique o número da porta de origem**, selecione **este ou intervalo de porta de origem**. Na caixa de texto que o acompanha, digite o intervalo de portas reservado para transmissões de áudio. Por exemplo, se você reservadas portas 49152 através de portas 57500 para tráfego de áudio, insira o intervalo de portas usando este formato: **49152:57500**. Clique em **Concluir**.

> [!NOTE]  
> O valor DSCP de 46 é relativamente arbitrário: Embora DSCP 46 é frequentemente usado para marcar os pacotes de áudio, você não precisará usar o DSCP 46 para comunicações de áudio. Se você já implementou QoS e você estiver usando um código DSCP diferente para áudio (por exemplo, 40 de DSCP), você deve configurar sua política de qualidade de serviço para usar esse mesmo código (ou seja, 40 para áudio). Se você estiver implementando apenas agora Quality of Service, é recomendável que você use DSCP 46 para áudio, simplesmente porque esse valor geralmente é usado para marcar os pacotes de áudio.

Depois que você criou a política de QoS para o tráfego de áudio, você deve criar uma segunda política para o tráfego de vídeo (e, opcionalmente, uma terceira política para gerenciar o tráfego de compartilhamento de aplicativo). Para criar uma política para vídeo, siga o mesmo procedimento básico que seguiu quando criar a política de áudio, tornando essas substituições:

  - Use um nome de política diferente (e único) (por exemplo, **Skype para Business Server vídeo**).

  - Defina o valor DSCP para **34** , em vez de 46. (Observe que você não precisa usar um valor DSCP de 34. O único requisito é que você use um valor DSCP diferente para vídeo que você usou para áudio.)

  - Use o intervalo de portas previamente configurados para o tráfego de vídeo. Por exemplo, se você tiver reservadas portas 57501 a 65535 para vídeo, defina o intervalo de portas a esta: **57501:65535**.

Se você decidir criar uma política para gerenciar o tráfego de compartilhamento de aplicativo, você deve criar uma terceira política, fazendo as seguintes substituições:

  - Use um nome de política diferente (e único) (por exemplo, **Skype para compartilhamento de aplicativos do Business Server**).

  - Defina o valor DSCP para **24** em vez de 46. (Novamente, você não precisará usar um valor DSCP de 24. O único requisito é que você use um valor DSCP diferente para compartilhamento de aplicativos que você usou para áudio ou vídeo.)

  - Use o intervalo de portas previamente configurados para o tráfego de vídeo. Por exemplo, se você tiver reservadas portas 40803 através de 49151 para compartilhamento de aplicativos, defina o intervalo de portas a esta: **40803:49151**.

As novas políticas que você criou não terão efeito até que a diretiva de grupo tenha sido atualizada no seu Skype para computadores Business Server. Embora a Política de Grupo seja periodicamente atualizada por si só, você pode forçar a atualização imediata executando o comando a seguir em cada computador em que a Política de Grupo deve ser atualizada:

    Gpupdate.exe /force

Este comando pode ser executado de dentro do Skype do Shell de gerenciamento do servidor de negócios ou de qualquer janela de comando que está sendo executado em credenciais de administrador. Para executar uma janela de comando com credenciais de administrador, clique em **Iniciar**, clique com o botão direito do mouse em **Prompt de Comando** e clique em **Executar como administrador**.

Para verificar se as novas políticas de QoS foram aplicadas, faça o seguinte:

1.  Em um Skype para computador Business Server, clique em **Iniciar**e, em seguida, clique em **Executar**.

2.  Na caixa de diálogo **Executar** , digite **regedit**e pressione ENTER.

3.  No Editor do registro, expanda o **computador**, **HKEY\_LOCAL\_máquina**, expanda **SOFTWARE**, expanda **diretivas**, expanda **Microsoft**, expanda **Windows**e clique em **QoS**. Em **QoS** , você verá chaves do registro para cada uma das políticas de QoS que você acabou de criar. Por exemplo, se você criou duas novas diretivas (um nomeado Skype para QoS de áudio do servidor de negócios) e a outro nomeado Skype para QoS de vídeo do Business Server, você deverá ver entradas do registro para Skype para QoS de áudio do servidor de negócios e Skype para QoS de vídeo do servidor de negócios.

Para ajudar a garantir que os pacotes de rede sejam marcados com o valor DSCP apropriado, você também deve criar uma nova entrada de registro em cada computador, Concluindo o seguinte procedimento:

1.  Clique em  **Iniciar ** e em  **Executar **.

2.  Na caixa de diálogo **Executar** , digite **regedit**e pressione ENTER.

3.  No Editor do registro, expanda **HKEY\_LOCAL\_máquina**, expanda **SYSTEM**, expanda **CurrentControlSet**, expanda **Serviços**e depois expanda **Tcpip**.

4.  Clique com o botão **Tcpip**, aponte para **novo**e clique em **chave**. Depois que a nova chave do registro é criada, digite **QoS**e pressione ENTER para renomear a chave.

5.  Com o botão direito **QoS**, aponte para **novo**e clique em **Valor de cadeia de caracteres**. Depois que o novo valor do registro é criado, digite **não use NLA**e pressione ENTER para renomear o valor.

6.  Clique duas vezes em **não use NLA**. Na caixa de diálogo **Editar cadeia de caracteres** , digite **1** na caixa **dados do valor** e clique em **Okey**.

7.  Feche o Editor do registro e reinicie seu computador.
