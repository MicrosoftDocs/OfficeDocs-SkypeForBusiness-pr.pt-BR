---
title: Implementar Qualidade de Serviço nos clientes do Microsoft Teams
author: jambirk
ms.author: jambirk
manager: Serdars
ms.date: 2/17/2019
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Implemente o Quality of Service (QoS) para clientes do Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 101deb10cf3d86dbc97116cad269556683d03be4
ms.sourcegitcommit: 946c77b847c1b2c5c43802ecfb0a918fa4f562d9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/15/2019
ms.locfileid: "31869842"
---
# <a name="set-qos-on-windows-clients"></a>Definir o QoS em clientes do Windows

Você pode usar a QoS baseada em diretivas dentro da diretiva de grupo para definir o intervalo de porta de origem para o valor DSCP predefinido no cliente equipes. Os intervalos de porta especificados na tabela a seguir são um ponto de partida para criar uma política para cada carga de trabalho.

_Recomendado de intervalos de porta inicial_

Tipo de tráfego de mídia| Intervalo de porta de origem do cliente |Protocolo|Valor de DSCP|Classe DSCP|
|:--- |:--- |:--- |:--- |:--- |
|Áudio| 50.000 – 50,019|TCP/UDP|46|Expedited Forwarding (EF)|
|Vídeo| 50,020 – 50,039|TCP/UDP|34|Assured Forwarding (AF41)|
|Compartilhamento de tela do aplicativo| 50,040 – 50,059|TCP/UDP|18|Assured Forwarding (AF21)|
| | | | |

Sempre que possível, configure as configurações de QoS baseada em diretivas dentro de um objeto de diretiva de grupo. As etapas a seguir serão bastante similares às [Configurando intervalos de porta e uma política de qualidade de serviço para seus clientes em Skype para Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), que tem alguns detalhes adicionais que talvez não seja necessários.

Para criar uma política de QoS de áudio para computadores associados a um domínio do Windows 10, primeiro faça logon em um computador no qual o gerenciamento de diretiva de grupo tenha sido instalado. Abra Gerenciamento de diretiva de grupo (clique em Iniciar, aponte para ferramentas administrativas e clique em gerenciamento de diretiva de grupo) e, em seguida, conclua as seguintes etapas:

1. Em gerenciamento de diretiva de grupo, localize o contêiner onde a nova diretiva deve ser criada. Por exemplo, se todos os computadores cliente estão localizados em uma unidade Organizacional denominada **clientes**, a nova diretiva deve ser criada na unidade Organizacional cliente.

2. Com o botão direito do contêiner apropriado e clique em **criar um GPO neste domínio e vinculá-lo aqui**.

3. Na caixa de diálogo **Novo GPO** , digite um nome para o novo objeto de diretiva de grupo na caixa **nome** e clique em **Okey**.

4. Clique com o botão a política recém-criada e clique em **Editar**.

5. No Editor de gerenciamento de diretiva de grupo, expanda **Configuração do computador**, expanda **Configurações do Windows**, do mouse em **QoS baseada em política**e clique em **Criar nova política**.

6. Na caixa de diálogo **QoS baseada em política** , na página de abertura, digite um nome para a nova política na caixa **nome** . Selecione **Especificar valor de DSCP** e defina o valor para **46**. Deixe **Especificar taxa de aceleração saída** desmarcada e clique em **Avançar**.

7. Na próxima página, selecione **apenas a aplicativos com este nome executável** e insira o nome **Teams.exe**e clique em **Avançar**. Essa configuração instrui a política priorizar apenas o tráfego do cliente equipes correspondente.

8. Na terceira página, certifique-se de que **qualquer endereço IP de origem** e de **qualquer endereço IP de destino** estão marcada e clique em **Avançar**. Estas duas configurações Certifique-se de que os pacotes serão gerenciados independentemente do computador (endereço IP) enviadas os pacotes e qual computador (endereço IP) receberá os pacotes.

9. Na página quatro, selecione **TCP e UDP** da lista suspensa **, selecione o protocolo que essa política de QoS se aplica** . TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) são os dois protocolos de rede mais comumente usados.

10. Sob o título, **Especifique o número da porta de origem**, selecione **este ou intervalo de porta de origem**. Na caixa de texto que o acompanha, digite o intervalo de portas reservado para transmissões de áudio. Por exemplo, se você reservadas portas 50000 através de portas 50019 para tráfego de áudio, insira o intervalo de portas usando este formato: **50000:50019**. Clique em **Concluir**.

11. Repita as etapas 5 a 10 para criar políticas para vídeo e compartilhamento de aplicativo/área de trabalho, substituindo os valores apropriados nas etapas 6 e 10.

As novas políticas que você criou não terão efeito até que a diretiva de grupo tenha sido atualizada em seus computadores cliente. Embora a diretiva de grupo for atualizada periodicamente por si só, você pode forçar uma atualização imediata, seguindo estas etapas:

1. Em cada computador para o qual você deseja atualizar a diretiva de grupo, abra um console de comando. Certifique-se de que o console de comando está definido para executar como administrador.

2. No prompt de comando, digite:

   ``` powershell
    gpupdate.exe /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a>Verifique se as marcações de DSCP no objeto de diretiva de grupo

Para verificar se os valores do objeto de diretiva de grupo foram definidos, execute as seguintes etapas.

1. Abra um console de comando. Certifique-se de que o console de comando está definido para executar como administrador.

2. No prompt de comando, digite:

   ``` powershell
   gpresult /R > gp.txt
   ```

   Isso irá gerar um relatório e enviá-la para um arquivo de texto chamado GP. txt. Como alternativa, você pode inserir o seguinte comando para produzir os mesmos dados em um relatório HTML mais legível chamado gp.html:

   ``` powershell
   gpresult /H >gp.html
   ```

   ![Captura de tela da janela do console, executando o comando gpresult.] (media/Qos-in-Teams-Image3.png "Captura de tela da janela do console, executando o comando gpresult.")

3. No arquivo gerado, procure por título de **Objetos de diretiva de grupo aplicados** e verifique se os nomes dos objetos de diretiva de grupo criados anteriormente estão na lista de diretivas aplicadas.

4. Abra o Editor do registro e vá para:

   HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS\

   Verifique se os valores para as entradas do Registro listadas na tabela 4.

   _Tabela 4. Valores para entradas de registro do Windows para QoS_

   |          Nome          |  Tipo  |    Dados     |
   |         :---:          |:---:   |    :---:    |
   |    Nome do Aplicativo    | REG_SZ |  Teams.exe  |
   |       Valor de DSCP       | REG_SZ |     46      |
   |        IP Local        | REG_SZ |     \*      |
   | Comprimento do Prefixo IP Local | REG_SZ |     \*      |
   |       Porta Local       | REG_SZ | 50000-50019 |
   |        Protocolo        | REG_SZ |     \*      |
   |       IP Remoto        | REG_SZ |     \*      |
   |    Prefixo IP remoto    | REG_SZ |     \*      |
   |      Porta Remota       | REG_SZ |     \*      |
   |     Taxa de Aceleração      | REG_SZ |     -1      |

5. Verificar se o valor para a entrada de nome do aplicativo está correto para o cliente que você está usando e verificar que o valor DSCP e a porta Local entradas reflitam as configurações no objeto de diretiva de grupo.
