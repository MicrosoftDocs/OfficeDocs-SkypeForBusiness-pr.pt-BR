---
title: Configurando intervalos de porta e uma política de Qualidade de Serviço para seus servidores de Conferência, Aplicativo e Mediação
ms.reviewer: ''
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Este artigo descreve como configurar intervalos de porta e uma política de Qualidade de Serviço para seus servidores de Conferência, Aplicativo e Mediação.
ms.openlocfilehash: ea7e150824ff3816c99a26bb92c165e9b237b5fe
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62410754"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers"></a>Configurando intervalos de porta e uma política de Qualidade de Serviço para seus servidores de Conferência, Aplicativo e Mediação

Este artigo descreve como configurar intervalos de porta e uma política de Qualidade de Serviço para seus servidores de Conferência, Aplicativo e Mediação.

## <a name="configure-port-ranges"></a>Configurar intervalos de porta

Para implementar a Qualidade de Serviço, você deve configurar intervalos de porta idênticos para compartilhamento de áudio, vídeo e aplicativo em seus servidores de Conferência, Aplicativo e Mediação; além disso, esses intervalos de porta não devem se sobrepor de forma alguma. Para usar um exemplo simples, imagine que você utilize as portas de 10000 a 10999 para vídeo nos seus servidores de Conferência. Isso significa que você deve reservar as portas de 10000 a 10999 para vídeo nos seus servidores de Aplicativo e de Mediação. Caso não o faça, a Qualidade do serviço não funcionará como esperado.

De forma semelhante, imagine que você reserva as portas de 10000 a 10999 para vídeo e, em seguida, reserva as portas de 10500 a 11999 para áudio. Isso pode gerar problemas na Qualidade do serviço porque os intervalos de porta se sobrepõem. Com a QoS, cada modalidade deve ter um conjunto exclusivo de portas: se você usar as portas 10000 a 10999 para vídeo, então você terá que usar um intervalo diferente (por exemplo, 11000 a 11999, para áudio).

Por padrão, os intervalos de porta de áudio e vídeo não se sobrepõem ao Skype for Business Server; no entanto, os intervalos de porta atribuídos ao compartilhamento de aplicativos se sobrepõem aos intervalos de porta de áudio e vídeo. (O que, por sua vez, significa que nenhum desses intervalos é exclusivo.) Você pode verificar os intervalos de porta existentes para seus servidores de Conferência, Aplicativo e Mediação executando os três comandos a seguir no Shell de Gerenciamento Skype for Business Server:

  Get-CsService -ConferencingServer | Select-Object Identidade, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
  Get-CsService -ApplicationServer | Select-Object Identidade, AudioPortStart, AudioPortCount
    
  Get-CsService -MediationServer | Select-Object Identidade, AudioPortStart, AudioPortCount

> [!WARNING]  
> Como você pode observar nos comandos precedentes, é atribuído a cada tipo de porta – áudio, vídeo e compartilhamento de aplicativo – dois valores separados de propriedade: a porta inicial e a contagem de porta. A porta inicial indica a primeira porta usada por essa modalidade; por exemplo, se a porta inicial de áudio é igual a 50000, significa que a primeira porta usada para o tráfego de áudio é a porta 50000. Se a contagem de porta de áudio for 2 (que não é um valor válido, mas é usada aqui para fins de ilustração), isso significa que apenas duas portas são alocadas para áudio. Se a primeira porta é a porta 50000 e há um total de duas portas, significa que a segunda porta será a porta 50001 (os intervalos de porta devem ser contíguos). Dessa forma, o intervalo de porta para áudio seria da porta 50000 até a 50001, ambas incluídas.<BR><br>Observe que o servidor de Aplicativo e o servidor de Mediação suportam QoS somente para áudio; você não precisa modificar as portas de vídeo ou as de compartilhamento de aplicativo nos seus servidores de Aplicativo ou de Mediação.

Se você executar os três comandos anteriores, verá que os valores de porta padrão para Skype for Business Server estão configurados desta forma:

<table>
<colgroup>
</colgroup>
<thead>
<tr class="header">
<th>Propriedade</th>
<th>Servidor de Conferência</th>
<th>Servidor de Aplicativo</th>
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

Conforme mencionado anteriormente, ao configurar Skype for Business Server portas para QoS, você deve garantir que: 1) as configurações da porta de áudio sejam idênticas em seus servidores de Conferência, Aplicativo e Mediação; e, 2) intervalos de porta não se sobrepõem. Se você observar com atenção a tabela anterior, verá que os intervalos de porta são idênticos nos três tipos de servidores. Por exemplo, a porta inicial de áudio está configurada para a porta 49152 em cada tipo de servidor e o número total de portas reservadas para áudio em cada servidor também é igual: 8348. No entanto, os intervalos de porta se sobrepõem: as portas de áudio iniciam na porta 49152, mas o mesmo acontece com as portas configuradas para o compartilhamento de aplicativo. Para usar a Qualidade do serviço de forma ótima, o compartilhamento de aplicativo deve ser reconfigurado para que use um único intervalo de porta. Por exemplo, você poderia configurar o compartilhamento de aplicativo para iniciar na porta 40803 e para usar as portas 8348. (Por que as portas 8348? Se você adicionar esses valores juntos - 40803 + 8348 - isso significa que o compartilhamento de aplicativos usará as portas 40803 por meio da porta 49150. Já que as portas de áudio não começam até a porta 49152, você não terá mais nenhum intervalo de porta em sobreposição.)

Depois de selecionar o novo intervalo de porta para compartilhamento de aplicativos, você pode fazer a alteração usando o cmdlet Set-CsConferencingServer de usuário. Essa alteração não precisa ser feita no seus servidores de Aplicativo ou de Mediação, já que esses servidores não manipulam o tráfego do compartilhamento de aplicativos. Você precisa alterar somente os valores de porta nesses servidores caso decida reatribuir as portas usadas no tráfego de áudio.

Para modificar os valores de porta para compartilhamento de aplicativos em um único servidor de Conferência, execute um comando semelhante a este no Shell de Gerenciamento Skype for Business Server:

  **Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348**

Se quiser fazer essas alterações em todos os servidores de Conferência, execute este comando em vez disso:

  **Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_. Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}**

Depois de alterar as configurações da porta, você deve parar e reiniciar cada serviço afetado pelas alterações.

Não é obrigatório que seus servidores de Conferência, de Aplicativo e de Mediação compartilhem os mesmos intervalos de porta; o único requisito é que você configure intervalos de porta únicos em todos os servidores. No entanto, a administração será normalmente mais fácil se você usar os mesmo conjuntos de portas em todos os servidores.

## <a name="configure-a-quality-of-service-policy-in-skype-for-business-server-for-your-conferencing-application-and-mediation-servers"></a>Configurar uma política de Qualidade de Serviço no Skype for Business Server para seus servidores de Conferência, Aplicativo e Mediação

Configurar intervalos de porta facilita o uso da Qualidade de Serviço, garantindo que todo o tráfego de um tipo especificado (por exemplo, todo o tráfego de áudio) percorra o mesmo conjunto de portas. Isso facilita para o sistema identificar e marcar um dado pacote: se a porta 49152 estiver reservada para tráfego de áudio, então qualquer pacote que passar pela porta 49152 poderá ser marcado com um código DSCP indicando que é um pacote de áudio. Por sua vez, isso permite que os roteadores identifiquem o pacote como um pacote de áudio, e forneçam a ele uma prioridade maior que a de pacotes não marcados (como pacotes usados para copiar um arquivo de um servidor a outro).

No entanto, restringir simplesmente um conjunto de portas para um tipo de tráfego específico não faz com que os pacotes que viajam através dessas portas sejam marcados com o código DSCP apropriado. Além de definir intervalos de porta, você também deve criar políticas de Qualidade de Serviço que especifiquem o código DSCP a ser associado a cada intervalo de portas. Para Skype for Business Server, isso normalmente significa criar duas políticas: uma para áudio e outra para vídeo.

As políticas de Qualidade de Serviço são criadas e gerenciadas com mais facilidade usando a Política de Grupo. (Essas mesmas políticas podem também ser criadas usando políticas de segurança local. No entanto, isso exige que você repita o mesmo procedimento em cada computador.) Seu conjunto inicial de políticas de QoS (uma para áudio e outra para vídeo Skype for Business Server) deve ser aplicada somente a computadores que executam o servidor de conferência, servidor de aplicativos e/ou serviços de servidor de Mediação. Se todos esses computadores estão localizados na mesma UO do Active Directory, você pode simplesmente atribuir o novo objeto de Política de Grupo (GPO) a essa OU. Como alternativa, você pode fazer outro procedimento para abordar a nova política para os computadores especificados; por exemplo, você pode colocar os computadores apropriados em um grupo de segurança, depois usar a filtragem de segurança de Política de Grupo para aplicar a GPO apenas a esse grupo de segurança.

Para criar uma política de Qualidade de Serviço para gerenciar áudio, faça logoff em um computador onde o Gerenciamento de Política de Grupo foi instalado. Abra o Gerenciamento de Política de Grupo (clique em **Iniciar**, aponte para Ferramentas Administrativas e clique em Gerenciamento de Política de **Grupo**) e conclua o seguinte procedimento:

1.  No Gerenciamento de Política de Grupo, localize o contêiner em que a nova política deve ser criada. Por exemplo, se todos os seus computadores Skype for Business Server estão localizados em uma UO chamada Skype for Business Server, a nova política deve ser criada na UO Skype for Business Server.

2.  Clique com o botão direito do mouse no contêiner apropriado e clique em **Criar um GPO neste domínio e vincule-o aqui**.

3.  Na caixa **de diálogo Novo GPO**, digite um nome para o novo objeto de Política de Grupo  na caixa Nome (por exemplo, Skype for Business Server **QoS**) e clique em **OK**.

4.  Clique com o botão direito do mouse na política recém-criada e clique em **Editar**.

5.  No Editor de Gerenciamento de Política de Grupo, expanda **Configuração do computador**, expanda **Políticas**, expanda **Configurações do Windows**, clique com o botão direito em **QoS baseado em política**, e depois clique em **Criar nova política**.

6.  Na caixa **de diálogo QoS** baseada em política, na página de abertura, digite um nome para a nova política (por exemplo, **Skype for Business Server QoS**) na **caixa Nome.** Selecione **Especificar valor de DSCP** e defina o valor como **46**. Deixe a opção **Especificar Taxa de Aceleração de Saída** desmarcada e clique em **Avançar**.

7.  Na próxima página, certifique-se de que **Todos os aplicativos** estão selecionados e clique em **Próximo**. Isso garante que todos os aplicativos compararão os pacotes da porta especificada com o código DSCP especificado.

8.  Na terceira página, certifique-se de que qualquer endereço IP de origem e qualquer endereço **IP** de destino estão selecionados e clique em **Próximo**. Essas duas configurações garantem que os pacotes serão gerenciados independente de qual computador (endereço IP) tenha os enviado e de qual computador (endereço IP) os receberá.

9.  Na página quatro, selecione **TCP e UDP** na lista suspensa **Selecione o protocolo ao qual esta política de QoS se aplica**. TCP (Protocolo de Controle de Transmissão) e UDP (User Datagram Protocol) são os dois protocolos de rede mais usados pelo Skype for Business Server e seus aplicativos cliente.

10. No cabeçalho **Especifique o número da porta de origem**, selecione **Desta porta ou intervalo de origem**. Na caixa de texto acompanhante, digite o intervalo de porta reservado para transmissões de áudio. Por exemplo, se você reservou as portas 49152 por meio das portas 57500 para tráfego de áudio, insira o intervalo de portas usando esse formato: **49152:57500**. Clique em **Concluir**.

> [!NOTE]  
> O valor DSCP de 46 é de certa forma arbitrário: embora DSCP 46 seja usado com frequência para marcar pacotes de áudio, você não precisa usar o DSCP 46 para comunicação de áudio. Se você já implementou a QoS e está usando um código DSCP diferente para áudio (por exemplo, DSCP 40), você deve configurar sua política de Qualidade de Serviço para usar esse mesmo código (ou seja, 40 para áudio). Se só agora você estiver implementado a Qualidade de Serviço, recomendamos que você use DSCP 46 para áudio, simplesmente porque este valor é o mais comumente usado para marcar pacotes de áudio.

Depois de criar a política QoS para tráfego de áudio, crie uma segunda política para tráfego de vídeo (e, opcionalmente, uma terceira política para gerenciar o tráfego de compartilhamento de aplicativos). Para criar uma política para vídeo, siga o mesmo procedimento básico da criação da política de áudio, fazendo as seguintes substituições:

  - Use um nome de política diferente (e exclusivo) (por exemplo, **Skype for Business Server Vídeo**).

  - Defina o valor do DSCP como **34** em vez de 46 (observe que você não precisa usar o valor 34 para o DSCP. O único requisito é usar para o vídeo um valor de DSCP diferente do valor usado para o áudio).

  - Use o intervalo de portas configurado anteriormente para tráfego de vídeo. Por exemplo, se você tiver reservado as portas 57501 a 65535 para vídeo, de definir o intervalo de portas como este: **57501:65535**.

Se você decidir criar uma política para gerenciar o tráfego de compartilhamento de aplicativos, deverá criar uma terceira política, fazendo as seguintes substituições:

  - Use um nome de política diferente (e exclusivo) (por exemplo, **Skype for Business Server Compartilhamento de Aplicativos**).

  - Defina o valor do DSCP como **24** em vez de 46 (novamente, não é necessário usar o valor 24 para o DSCP. O único requisito é usar para o compartilhamento de aplicativos um valor de DSCP diferente do valor usado para áudio e vídeo).

  - Use o intervalo de portas configurado anteriormente para tráfego de vídeo. Por exemplo, se você reservou as portas 40803 a 49151 para compartilhamento de aplicativos, de definir o intervalo de portas como este: **40803:49151**.

As novas políticas criadas não terão efeito até que a Política de Grupo seja atualizada em seus computadores Skype for Business Server de grupo. Embora a Política de Grupo seja atualizada periodicamente sozinha, você pode forçar uma atualização imediata executando o comando a seguir em cada computador em que for necessário atualizar a Política de Grupo:

  **Gpupdate.exe /force**

Esse comando pode ser executado de dentro do Shell de Gerenciamento Skype for Business Server ou de qualquer janela de comando que está sendo executado sob credenciais de administrador. Para executar uma janela de comando sob credenciais de administrador, clique em **Iniciar**, clique com o botão direito em **Prompt de comando**, e depois em **Executar como administrador**.

Para verificar se as novas políticas de QoS foram aplicadas, faça o seguinte:

1.  Em um Skype for Business Server computador, clique em **Iniciar** e clique em **Executar**.

2.  Na caixa **de diálogo** Executar, digite **regedit** e pressione ENTER.

3.  No Editor de Registro, expanda **Computador**, **expanda HKEYLOCALMACHINE\_\_**, **expanda SOFTWARE****,** Expanda Políticas, **Microsoft****, expanda** Windows e clique em **QoS**. Em **QoS**, você deverá ver chaves de registro para cada política de QoS criada. Por exemplo, se você criou duas novas políticas (uma chamada Skype for Business Server QoS de áudio e outra chamada QoS de vídeo Skype for Business Server), você deverá ver entradas de registro para Skype for Business Server QoS de áudio e Skype for Business Server QoS de vídeo.

Para ajudar a garantir que os pacotes de rede sejam marcados com o valore DSCP correto, você também deve criar uma nova entrada de registro em cada computador, concluindo o procedimento a seguir:

1.  Clique em **Iniciar** e em **Executar**.

2.  Na caixa **de diálogo** Executar, digite **regedit** e pressione ENTER.

3.  No Editor do Registro, **expanda HKEYLOCALMACHINE\_\_**, expanda **SYSTEM**, **CurrentControlSet**, expanda **serviços** e **expanda Tcpip**.

4.  Clique com o botão direito em **Tcpip**, aponte para **Novo** e clique em **Chave**. Depois que a nova chave do Registro for criada, digite **QoS** e pressione ENTER para renomear a chave.

5.  Clique com o botão direito em **QoS**, aponte para **Novo** e clique em **Valor da Sequência**. Depois que o novo valor do Registro for criado, digite **Não usar NLA** e pressione ENTER para renomear o valor.

6.  Clique duas **vezes em Não usar NLA**. Na caixa **de diálogo Editar Cadeia** de Caracteres, digite **1** na caixa **Dados Valor** e clique em **OK**.

7.  Feche o Editor do Registro e reinicie o computador.
