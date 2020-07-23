---
title: Aplicativo faça talkie no Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Como configurar o aplicativo faça talkie no Microsoft Teams, a partir de uma perspectiva ITAdmin.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4154a3ad30bf18de934f0fe5a23bbabc94fc76eb
ms.sourcegitcommit: 863347fb6e5916d8d936adc4ddcebb2e32a91d1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2020
ms.locfileid: "45229047"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>Aplicativo faça de conversas no Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

O aplicativo faça talkie no Teams oferece comunicação instantânea Push-to-Talk (PTT) para sua equipe e está disponível no modo de visualização pública no Android. O faça talkie permite que os usuários se conectem com sua equipe usando os mesmos canais subjacentes dos quais são membros. Somente os usuários que se conectam ao faça talkie em um canal tornam-se participantes e podem se comunicar uns com os outros usando o push para conversar, um por vez.

Com o faça de trabalho no Microsoft Teams, os trabalhadores de primeira mão podem se comunicar com uma experiência PTT conhecida sem precisar ter rádios em massa, e o faça de fala funciona em qualquer lugar com conexão WiFi ou celular à Internet.

## <a name="getting-started"></a>Introdução

### <a name="deploying-walkie-talkie"></a>Implantando o faça talkie

Durante a visualização pública, o faça talkie não está pré-instalado. Para habilitar esse recurso para os usuários de sua organização, você precisa adicionar faça a [política de configuração do aplicativo](teams-app-setup-policies.md)   atribuída a usuários do centro de [Administração do teams](https://admin.teams.microsoft.com/).

Uma vez habilitada, o faça talkie estará disponível no aplicativo Android em 48 horas.

### <a name="adding-walkie-talkie-to-your-app-list"></a>Adicionando o faça Talkse à sua lista de aplicativos

No centro de administração do Microsoft Teams, em políticas de configuração do **aplicativo do teams**  >  **Setup policies**, você deve **permitir a fixação do usuário** definida como **ativado**. Em seguida, na seção aplicativos fixos, clique em **+ adicionar aplicativos**.

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="Mostra a seção de aplicativos fixos e o botão adicionar aplicativos a ser selecionado.":::

No painel **adicionar aplicativos fixos** que aparece à direita, use a caixa de texto de **pesquisa** para procurar faça fala. Quando você tiver um resultado de pesquisa, clique no botão **Adicionar** à direita do nome para adicioná-lo à sua lista.

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Mostra a barra lateral adicionar aplicativos fixos com faça inserida no painel de pesquisa e o aplicativo de fala do faça nos resultados da pesquisa, com o botão Adicionar ao lado dele.":::

O aplicativo faça talkie agora deve aparecer na lista de aplicativos fixos e estar disponível para ser usado quando você clicar no botão **salvar** .

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="Mostra a lista de aplicativos fixos com o aplicativo de faça de fala adicionado e o botão salvar abaixo da lista.":::

### <a name="network-documentation"></a>Documentação da rede

O faça Talk in Teams requer conectividade à Internet e as condições de rede abaixo delas são necessárias para obter a melhor experiência possível.

Latência (RTT) < 300ms | < de Tremulação do 30ms | Perda de pacotes < 1%

Conforme observado acima, a qualidade da mídia em tempo real em uma rede IP é bastante afetada pela qualidade da conectividade de rede, mas especialmente pela quantidade de:

- **Latência** -é o tempo que leva para obter um pacote IP do ponto a ao ponto B na rede. Esse atraso de propagação de rede está essencialmente ligado à distância física entre os dois pontos e a velocidade da luz, incluindo a sobrecarga adicional sofrida pelos vários roteadores intermediários. A latência é medida como RTT (tempo de ida e volta).
- **Perda de pacote** -geralmente é definido como uma porcentagem de pacotes perdidos em uma determinada janela de tempo. A perda de pacotes afeta diretamente a qualidade do áudio, desde pequenos pacotes perdidos individuais com quase nenhum impacto, até perdas de Burst back-to-back que causam o recorte de áudio completo.
- **Tremulação** -esta é a alteração média em atraso entre pacotes sucessivos.

O uso de dados esperado do faça talkie é cerca de 20KB/s ao enviar ou receber áudio. Quando ocioso, o uso esperado de dados de faça de é insignificant.

### <a name="walkie-talkie-devices"></a>Dispositivos faça de fala

Em geral, os funcionários de primeira mão precisam falar e receber chamadas do faça Talk, mesmo quando seus telefones estiverem bloqueados. Essa experiência é possível por meio de dispositivos especializados com um botão PTT dedicado.

- Fones
  - Fone de ouvido com microfone com fio ([Klein eletrônicos](https://www.kleinelectronics.com/poc-accessories/mtwt/))
  - Fones de ouvido sem fio ([Jabra BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie))
- Telefones resistentes
  - Samsung Galaxy XCover pro
    - [Mais informações](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/).
    - [Guia de configuração](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm).

> [!NOTE]
> Esses dispositivos não são certificados para equipes. Elas foram validadas para trabalhar com o Microsoft Teams faça de conversar.

### <a name="license-requirements"></a>Requisitos de licença

O aplicativo faça talkie está incluído em todas as licenças pagas do teams nas [assinaturas do Office 365](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing). Para obter mais informações sobre como obter o Microsoft Teams, confira [como faço para obter acesso ao Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)?

> [!NOTE]
> Certos recursos avançados podem exigir licenciamento adicional. Por exemplo, a integração com o Samsung Galaxy XCover pro requer uma licença do Knox.

## <a name="further-information"></a>Mais informações

- ITAdmins pode manter o controle sobre quem está usando o faça Talkse através de políticas de aplicativo.
- Se o trabalhador da primeira mão estiver usando dados móveis para se comunicar por meio do Teams, o faça Talkse usará o mesmo método.
- O faça Talkment deve funcionar bem em situações de pouca largura de banda ou em situações em que seu smartphone está conectado e funcionando. Façaa a fala não funcionará quando não houver conectividade alguma.

Para ler mais sobre a experiência do usuário final, consulte:

- [Introdução ao Teams faça a Palestrat](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [Comunique-se com sua equipe com o faça talkie](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
