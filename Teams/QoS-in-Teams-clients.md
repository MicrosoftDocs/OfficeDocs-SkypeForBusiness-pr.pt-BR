---
title: Implementar qoS (qualidade de serviço) em clientes do Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: Saiba como usar a QoS (Qualidade de Serviço) para otimizar o tráfego de rede para o cliente da área de trabalho do Microsoft Teams.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: 70dbc5794fe64a1afed86bc82d0005ad7d510c5f
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2022
ms.locfileid: "66563919"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams-clients"></a>Implementar qoS (qualidade de serviço) em clientes do Microsoft Teams

Você pode usar a QoS (Qualidade de Serviço) baseada em políticas Política de Grupo definir o intervalo de portas de origem para o valor DSCP predefinido no cliente do Teams. Os intervalos de portas especificados na tabela a seguir são um ponto de partida para criar uma política para cada carga de trabalho.

*Tabela 1. Intervalos de portas iniciais recomendados*

|Tipo de tráfego de mídia| Intervalo de portas de origem do cliente  |Protocolo|Valor DSCP|Classe DSCP|
|:--- |:--- |:--- |:--- |:--- |
|Áudio| 50.000–50.019|TCP/UDP|46|Expedited Forwarding (EF)|
|Vídeo| 50.020–50.039|TCP/UDP|34|Assured Forwarding (AF41)|
|Compartilhamento de tela/aplicativo| 50.040-50.059|TCP/UDP|18|Assured Forwarding (AF21)|
| | | | | |

Sempre que possível, defina as configurações de QoS baseadas em políticas em um Política de Grupo objeto. As etapas [a seguir são muito semelhantes](/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10) à configuração de intervalos de portas e a uma política de Qualidade de Serviço para seus clientes no Skype for Business Server, que tem alguns detalhes adicionais que podem não ser necessários.

Para criar uma política de áudio de QoS para computadores Windows 10 domínio, primeiro faça logon em um computador no qual o Política de Grupo Management foi instalado. Abra Política de Grupo Gerenciamento (clique em Iniciar, aponte para Ferramentas Administrativas e, em seguida, clique em Política de Grupo Gerenciamento) e conclua as seguintes etapas:

1. No Política de Grupo, localize o contêiner onde a nova política deve ser criada. Por exemplo, se todos os computadores cliente estiverem localizados em uma UO chamada **Clientes**, a nova política deverá ser criada na UO de Clientes.

1. Clique com o botão direito do mouse no contêiner apropriado e clique em **Criar um GPO neste domínio e vincule-o aqui**.

1. Na caixa **de diálogo Novo GPO**, digite um nome para o novo objeto Política de Grupo na caixa Nome e  clique em **OK**.

1. Clique com o botão direito do mouse na política recém-criada e clique em **Editar**.

1. No Editor Política de Grupo Gerenciamento **, expanda** a Configuração do Computador, expanda As Configurações do **Windows**, clique com o botão direito do mouse em **QoS** baseada em política e clique em Criar **nova política**.

1. Na caixa **de diálogo QoS** baseada em política, na página de abertura, digite um nome para a nova política na **caixa** Nome. Selecione **Especificar Valor DSCP** e defina o valor como **46**. Deixe **Especificar a Taxa de Limitação de Saída** desmarcada e clique em **Avançar**.

1. Na próxima página, selecione **Somente aplicativos com esse nome executável** , insira **o nomeTeams.exe** e clique em **Avançar**. Essa configuração instrui a política a priorizar apenas o tráfego correspondente do cliente do Teams.

1. Na terceira página, verifique se qualquer endereço **IP** de origem e qualquer endereço **IP** de destino estão selecionados e clique em **Avançar**. Essas duas configurações garantem que os pacotes sejam gerenciados independentemente de qual computador (endereço IP) enviou os pacotes e qual computador (endereço IP) receberá os pacotes.

1. Na página quatro, selecione **TCP e UDP** na lista suspensa Selecionar o protocolo que essa política de **QoS aplica** . TCP (Protocolo de Controle de Transmissão) e UDP (Protocolo de Datagrama de Usuário) são os dois protocolos de rede mais usados.

1. No título Especificar **o número da porta de origem**, selecione **Desta porta ou intervalo de origem**. Na caixa de texto que o acompanha, digite o intervalo de portas reservado para transmissões de áudio. Por exemplo, se você reservou portas 50000 por meio das portas 50019 para tráfego de áudio, insira o intervalo de portas usando este formato: **50000:50019**. Clique em **Concluir**.

1. Repita as etapas 5 a 10 para criar políticas para Compartilhamento de Vídeo e Aplicativo/Área de Trabalho, substituindo os valores apropriados nas etapas 6 e 10.

As novas políticas que você criou não entrarão em vigor até que Política de Grupo tenha sido atualizado em seus computadores cliente. Embora Política de Grupo atualize periodicamente por conta própria, você pode forçar uma atualização imediata seguindo estas etapas:

1. Em cada computador para o qual você deseja atualizar Política de Grupo, abra um Prompt de Comando como administrador (*Executar como administrador*).

1. No prompt de comando, insira

   ```console
   gpupdate /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a>Verificar marcações DSCP no Política de Grupo objeto

Para verificar se os valores do objeto Política de Grupo foram definidos, execute as seguintes etapas:

1. Abra um prompt de comando como administrador (*Executar como administrador*).

1. No prompt de comando, insira

   ```console
   gpresult /R > gp.txt
   ```

   Isso gerará um relatório de GPOs aplicados e o enviará para um arquivo de texto chamado *gp.txt*.

   Para um relatório HTML mais legível *chamadogp.html*, insira o seguinte comando:

   ```console
   gpresult /H gp.html
   ```

1. No arquivo gerado, procure o título **Applied Política de Grupo Objects** e verifique se os nomes dos objetos Política de Grupo criados anteriormente estão na lista de políticas aplicadas.

1. Abra o Editor do Registro e vá para

   HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Windows\\QoS

   Verifique os valores das entradas do Registro listadas na Tabela 2.

   *Tabela 2. Valores para entradas do Registro do Windows para QoS*

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

1. Verifique se o valor da entrada nome do aplicativo está correto para o cliente que você está usando e verifique se as entradas Valor DSCP e Porta Local refletem as configurações no objeto Política de Grupo.


## <a name="related-topics"></a>Tópicos relacionados

[Implementar qoS (qualidade de serviço) no Teams](QoS-in-Teams.md)