---
title: Implementar Qualidade de Serviço nos clientes do Microsoft Teams
author: jambirk
ms.author: jambirk
manager: Serdars
ms.date: 2/17/2019
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Implementar a QoS (qualidade de serviço) para clientes do Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 43a4c7ea45fe0feabbe8851cde944a70994829da
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836481"
---
# <a name="set-qos-on-windows-clients"></a>Definir o QoS em clientes do Windows

Você pode usar a QoS baseada em política dentro da política de grupo para definir o intervalo de porta de origem para o valor DSCP predefinido no cliente do teams. Os intervalos de porta especificados na tabela a seguir são um ponto de partida para criar uma política para cada carga de trabalho.

*Tabela 1. Intervalos de portas iniciais recomendados*

|Tipo de tráfego de mídia| Intervalo de porta de origem do cliente |Protocolo|Valor de DSCP|Classe DSCP|
|:--- |:--- |:--- |:--- |:--- |
|Áudio| 50000 – 50019|TCP/UDP|46|Expedited Forwarding (EF)|
|Vídeo| 50,020–50,039|TCP/UDP|34|Assured Forwarding (AF41)|
|Compartilhamento de tela/aplicativo| 50,040–50,059|TCP/UDP|dezoito|Encaminhamento garantido (AF21)|
| | | | | |

Sempre que possível, configure as configurações de QoS baseadas em políticas em um objeto de política de grupo. As etapas a seguir são muito parecidas com a [configuração de intervalos de porta e uma política de qualidade de serviço para seus clientes no Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), que tem alguns detalhes adicionais que podem não ser necessários.

Para criar uma política de áudio QoS para computadores Windows 10 associados a um domínio, primeiro faça logon em um computador no qual o gerenciamento de política de grupo foi instalado. Abra gerenciamento de política de grupo (clique em Iniciar, aponte para ferramentas administrativas e clique em gerenciamento de política de grupo) e conclua as seguintes etapas:

1. No gerenciamento de política de grupo, localize o contêiner em que a nova política deve ser criada. Por exemplo, se todos os seus computadores cliente estiverem localizados em uma UO chamada **clientes**, a nova política deve ser criada na ou clientes.

1. Clique com o botão direito do mouse no contêiner apropriado e, em seguida, clique em **criar um GPO neste domínio e vincule-o aqui**.

1. Na caixa de diálogo **novo GPO** , digite um nome para o novo objeto de política de grupo na caixa **nome** e clique em **OK**.

1. Clique com o botão direito do mouse na política recém-criada e, em seguida, clique em **Editar**.

1. No editor de gerenciamento de política de grupo, expanda **configuração do computador**, expanda **configurações do Windows**, clique com o botão direito do mouse em **QoS baseado em política**e clique em **criar nova política**.

1. Na caixa de diálogo **QoS baseada em política** , na página de abertura, digite um nome para a nova política na caixa **nome** . Selecione **especificar valor DSCP** e defina o valor como **46**. Deixe **especificar a taxa de aceleração de saída** desmarcada e clique em **Avançar**.

1. Na próxima página, selecione **apenas aplicativos com esse nome executável** e insira o nome **Teams. exe**e clique em **Avançar**. Essa configuração instrui a política a priorizar somente o tráfego de correspondência do cliente do teams.

1. Na terceira página, verifique se **qualquer endereço IP de origem** e **qualquer endereço IP de destino** estão selecionados e clique em **Avançar**. Essas duas configurações garantem que os pacotes serão gerenciados independentemente de qual computador (endereço IP) enviou os pacotes e qual computador (endereço IP) receberá os pacotes.

1. Na página quatro, selecione **TCP e UDP** na lista suspensa **Selecione o protocolo ao qual esta política de QoS se aplica** . TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) são os dois protocolos de rede mais comumente usados.

1. Em título, **especifique o número da porta de origem**, selecione uma **destas portas de origem ou intervalo**. Na caixa de texto acompanhada, digite o intervalo de porta reservado para transmissões de áudio. Por exemplo, se você reservou portas 50000 pelas portas 50019 para tráfego de áudio, insira o intervalo de porta usando este formato: **50000:50019**. Clique em **Concluir**.

1. Repita as etapas 5-10 para criar políticas para compartilhamento de aplicativos/aplicativos e vídeo, substituindo os valores apropriados nas etapas 6 e 10.

As novas políticas que você criou não entrarão em vigor até que a política de grupo seja atualizada em seus computadores cliente. Embora a política de grupo seja atualizada periodicamente por conta própria, você pode forçar uma atualização imediata seguindo estas etapas:

1. Em cada computador para o qual você deseja atualizar a política de grupo, abra um prompt de comando como administrador (*Executar como administrador*).

1. No prompt de comando, insira

   ```console
   gpupdate /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a>Verificar marcações DSCP no objeto de política de grupo

Para verificar se os valores do objeto de política de grupo foram definidos, execute as seguintes etapas:

1. Abra um prompt de comando como administrador (*Executar como administrador*).

1. No prompt de comando, insira

   ```console
   gpresult /R > gp.txt
   ```

   Isso irá gerar um relatório de GPOs aplicados e enviá-lo a um arquivo de texto chamado *GP. txt*.

   Para obter um relatório HTML mais legível chamado *GP. html*, digite o seguinte comando:

   ```console
   gpresult /H gp.html
   ```

1. No arquivo gerado, procure o título objetos de **política de grupo aplicados** e verifique se os nomes dos objetos de política de grupo criados anteriormente estão na lista de políticas aplicadas.

1. Abra o editor do registro e vá para

   HKEY\_local\_Machine\\software\\\\Policies\\Microsoft\\Windows QoS

   Verifique os valores das entradas do registro listadas na tabela 2.

   *Tabela 2. Valores para entradas do registro do Windows para QoS*

   |          Nome          |  Tipo  |    Dados     |
   |         :---:          | :---:  |    :---:    |
   |    Nome do Aplicativo    | REG_SZ |  Teams.exe  |
   |       Valor de DSCP       | REG_SZ |     46      |
   |        IP Local        | REG_SZ |     \*      |
   | Comprimento do Prefixo IP Local | REG_SZ |     \*      |
   |       Porta Local       | REG_SZ | 50000-50019 |
   |        Protocolo        | REG_SZ |     \*      |
   |       IP Remoto        | REG_SZ |     \*      |
   |    Prefixo de IP remoto    | REG_SZ |     \*      |
   |      Porta Remota       | REG_SZ |     \*      |
   |     Taxa de Aceleração      | REG_SZ |     -1      |
   | | | |

1. Verifique se o valor da entrada do nome do aplicativo está correto para o cliente que você está usando e verifique se as entradas do valor DSCP e da porta local refletem as configurações no objeto de política de grupo.
