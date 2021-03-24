---
title: Implementar qoS (Qualidade de Serviço) em clientes do Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: Saiba como usar a QoS (Qualidade do Serviço) para otimizar o tráfego de rede para o cliente da área de trabalho do Microsoft Teams.
localization_priority: Normal
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
ms.openlocfilehash: 263e2d07992bd491259b82856413548fcd9741fd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094779"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams-clients"></a>Implementar qoS (Qualidade de Serviço) em clientes do Microsoft Teams

Você pode usar a QoS (Qualidade de Serviço baseada em política) na Política de Grupo para definir o intervalo de portas de origem para o valor DSCP predefinido no cliente teams. Os intervalos de porta especificados na tabela a seguir são um ponto de partida para criar uma política para cada carga de trabalho.

*Tabela 1. Intervalos de portas iniciais recomendados*

|Tipo de tráfego de mídia| Intervalo de portas de origem do cliente  |Protocolo|Valor DSCP|Classe DSCP|
|:--- |:--- |:--- |:--- |:--- |
|Áudio| 50.000–50.019|TCP/UDP|46|Expedited Forwarding (EF)|
|Vídeo| 50.020–50.039|TCP/UDP|34|Assured Forwarding (AF41)|
|Compartilhamento de tela/aplicativo| 50.040-50.059|TCP/UDP|18|Assured Forwarding (AF21)|
| | | | | |

Sempre que possível, configure as configurações de QoS baseadas em política em um objeto de Política de Grupo. As etapas a seguir são muito  [semelhantes à](/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10)Configuração de intervalos de porta e uma política de Qualidade de Serviço para seus clientes no Skype for Business Server , que tem alguns detalhes adicionais que podem não ser necessários.

Para criar uma política de áudio QoS para computadores Windows 10 ingressados no domínio, primeiro faça logoff em um computador no qual o Gerenciamento de Política de Grupo foi instalado. Abra o Gerenciamento de Política de Grupo (clique em Iniciar, aponte para Ferramentas Administrativas e clique em Gerenciamento de Política de Grupo) e conclua as seguintes etapas:

1. No Gerenciamento de Política de Grupo, localize o contêiner onde a nova política deve ser criada. Por exemplo, se todos os seus computadores clientes estão localizados em uma UO denominada **Clients**, a nova política deve ser criada na UO de Clientes.

1. Clique com o botão direito do mouse no contêiner apropriado e clique em **Criar um GPO neste domínio e vincule-o aqui**.

1. Na caixa de diálogo Novo **GPO,** digite um nome  para o novo objeto de Política de Grupo na caixa Nome e clique em **OK**.

1. Clique com o botão direito do mouse na política recém-criada e clique em **Editar**.

1. No Editor de Gerenciamento de Política de Grupo, **expanda** Configuração do **Computador, Configurações** do Windows, clique com o botão direito do mouse em **QoS** baseado em Política e clique em **Criar nova política**.

1. Na caixa **de diálogo QoS** baseada em política, na página de abertura, digite um nome para a nova política na **caixa** Nome. Selecione **Especificar Valor DSCP** e de definir o valor **como 46**. Deixe **Especificar Taxa de Aceleração de Saída** não eleita e clique em **Próximo**.

1. Na próxima página, selecione **Somente aplicativos** com esse nome executável e insira o **nome** Teams.exee clique em **Próximo**. Essa configuração instrui a política a priorizar apenas o tráfego correspondente do cliente do Teams.

1. Na terceira página, certifique-se de que qualquer endereço **IP** de origem e qualquer endereço **IP** de destino estão selecionados e clique em **Próximo**. Essas duas configurações garantem que os pacotes sejam gerenciados independentemente de qual computador (endereço IP) enviou os pacotes e qual computador (endereço IP) receberá os pacotes.

1. Na página quatro, selecione **TCP e UDP** na política Selecionar o protocolo que essa **política QoS aplica** à listada. TCP (Protocolo de Controle de Transmissão) e UDP (User Datagram Protocol) são os dois protocolos de rede mais usados.

1. Sob o título **Especifique o número da porta de** origem , selecione Nesta porta de **origem ou intervalo**. Na caixa de texto que acompanha, digite o intervalo de portas reservado para transmissões de áudio. Por exemplo, se você reservou as portas 50000 até as portas 50019 para tráfego de áudio, insira o intervalo de portas usando esse formato: **50000:50019**. Clique em **Concluir**.

1. Repita as etapas 5 a 10 para criar políticas para Compartilhamento de Vídeo e Aplicativo/Área de Trabalho, substituindo os valores apropriados nas etapas 6 e 10.

As novas políticas criadas não vigorarão até que a Política de Grupo seja atualizada em seus computadores clientes. Embora a Política de Grupo atualize periodicamente por conta própria, você pode forçar uma atualização imediata seguindo estas etapas:

1. Em cada computador para o qual você deseja atualizar a Política de Grupo, abra um Prompt de Comando como administrador (*Execute como administrador*).

1. No prompt de comando, digite

   ```console
   gpupdate /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a>Verificar marcações DSCP no objeto Diretiva de Grupo

Para verificar se os valores do objeto Diretiva de Grupo foram definidos, execute as seguintes etapas:

1. Abra um Prompt de Comando como administrador (*Execute como administrador*).

1. No prompt de comando, digite

   ```console
   gpresult /R > gp.txt
   ```

   Isso gerará um relatório de GPOs aplicados e o enviará para um arquivo de texto chamado *gp.txt*.

   Para um relatório HTML mais legível chamado *gp.html*, insira o seguinte comando:

   ```console
   gpresult /H gp.html
   ```

1. No arquivo gerado, procure o título **Objetos** de Política de Grupo Aplicados e verifique se os nomes dos objetos de Política de Grupo criados anteriormente estão na lista de políticas aplicadas.

1. Abra o Editor do Registro e vá para

   HKEY \_ LOCAL \_ MACHINE \\ Software \\ Policies \\ Microsoft \\ Windows \\ QoS

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
   |    Prefixo IP remoto    | REG_SZ |     \*      |
   |      Porta Remota       | REG_SZ |     \*      |
   |     Taxa de Aceleração      | REG_SZ |     -1      |
   | | | |

1. Verifique se o valor da entrada Nome do Aplicativo está correto para o cliente que você está usando e verifique se as entradas Valor DSCP e Porta Local refletem as configurações no objeto Política de Grupo.


## <a name="related-topics"></a>Tópicos relacionados

[Implementar qoS (qualidade de serviço) no Teams](QoS-in-Teams.md)