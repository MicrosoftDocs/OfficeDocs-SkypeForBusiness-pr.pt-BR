---
title: Aplicativo Walkie Talkie no Microsoft Teams
author: LanaChin
ms.author: v-lanachin
manager: samanro
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Como configurar o aplicativo Walkie Talkie no Microsoft Teams, de uma perspectiva do ITAdmin.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 27410562a32f620d8a20e058b0d460c1209e0121
ms.sourcegitcommit: ea9cbb8e32b7f23c17930eadc0a1dcbd906449ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/19/2022
ms.locfileid: "66842217"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>Aplicativo Walkie Talkie no Microsoft Teams

O aplicativo Walkie Talkie no Teams fornece comunicação PTT (push-to-talk) instantânea para sua equipe e agora está disponível no Android & iOS. O Walkie Talkie permite que os usuários se conectem com sua equipe usando os mesmos canais subjacentes dos quais são membros. Somente os usuários que se conectam ao Walkie Talkie em um canal se tornam participantes e podem se comunicar entre si usando o push-to-talk, um de cada vez.

Com o Walkie Talkie no Teams, os trabalhadores da linha de frente agora podem se comunicar com segurança com uma experiência de PTT familiar sem a necessidade de transportar rádios em massa, e Walkie Talkie trabalha em qualquer lugar com conectividade wi-fi ou de internet celular.

> [!NOTE]
> Walkie Talkie não está disponível atualmente na China.

## <a name="getting-started"></a>Introdução

### <a name="deploying-walkie-talkie"></a>Implantando Walkie Talkie

O Walkie Talkie tem suporte em dispositivos Android com dispositivos GMS (Google Mobile Services) e iOS.

### <a name="pin-walkie-talkie-to-teams"></a>Fixar Walkie Talkie no Teams

#### <a name="use-the-tailored-frontline-app-experience-to-pin-walkie-talkie-and-other-apps-to-teams"></a>Usar a experiência de aplicativo de linha de frente personalizada para fixar o Walkie Talkie e outros aplicativos no Teams

A experiência de aplicativo de linha de frente personalizada no Teams fixa os aplicativos mais relevantes no Teams para usuários que têm uma [licença F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt). Os aplicativos fixados incluem Walkie Talkie, Turnos, Tarefas e Aprovações. Por padrão, esse recurso está ativado, oferecendo aos funcionários da linha de frente uma experiência integrada e adaptada às suas necessidades.

Os aplicativos são fixados na barra de aplicativos , a barra ao lado do cliente da área de trabalho do Teams e na parte inferior dos clientes móveis do Teams, em que os usuários podem facilmente accessá-los.

Para saber mais, incluindo como a experiência funciona com as políticas de aplicativo definidas por você, confira Personalizar aplicativos [do Teams para seus funcionários da linha de frente](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json).

#### <a name="use-an-app-setup-policy-to-pin-walkie-talkie-to-teams"></a>Usar uma política de configuração de aplicativo para fixar o Walkie Talkie no Teams

As políticas de configuração de aplicativo permitem que você personalize o Teams para fixar aplicativos que são mais importantes para seus usuários em seus usuários.

Para fixar o aplicativo Walkie Talkie para seus usuários, você pode editar a política global (padrão em toda a organização) ou criar e atribuir uma política de configuração de aplicativo personalizada. Para saber mais, confira [Gerenciar políticas de configuração de aplicativos no Teams](teams-app-setup-policies.md).

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Captura de tela mostrando a adição do Walkie Talkie à lista de aplicativos fixados no painel Adicionar aplicativos fixados." lightbox="media/deploy-walkie-talkie-2.png":::

### <a name="network-documentation"></a>Documentação da rede

O Walkie Talkie no Teams requer conectividade com a Internet e, abaixo das condições de rede, são necessários para uma experiência ideal.

|Indicador | Obrigatório |
|---|---|
|Latência (RTT) | < 300 ms |
|Tremulação |< 30 ms |
|Perda de pacotes |< 1% |

Conforme mencionado acima, a qualidade da mídia em tempo real em uma rede IP é muito afetada pela qualidade da conectividade de rede, mas especialmente pela quantidade de:

- **Latência** – esse é o tempo necessário para obter um pacote IP do ponto A para o ponto B na rede. Esse atraso de propagação de rede é essencialmente vinculado à distância física entre os dois pontos e a velocidade da luz, incluindo mais sobrecarga tomada pelos vários roteadores entre eles. A latência é medida como RTT (Tempo de ida e volta).
- **Tremulação entre Chegadas** - Essa é a alteração média no atraso entre pacotes sucessivos.
- **Perda de** pacotes – isso geralmente é definido como uma porcentagem de pacotes que são perdidos em uma determinada janela de tempo. A perda de pacotes afeta diretamente a qualidade do áudio, desde pacotes perdidos pequenos e individuais que quase não têm impacto, até perdas de intermitência de volta para trás que causam corte de áudio completo.

O uso esperado de dados do Walkie Talkie é de cerca de 20 Kb/s ao enviar ou receber áudio. Quando ocioso, o uso de dados esperado do Walkie Talkie é insignificante.

### <a name="walkie-talkie-devices"></a>Dispositivos Walkie Talkie

Os trabalhadores da linha de frente geralmente precisam falar e receber chamadas do Walkie Talkie mesmo quando seus telefones estão bloqueados. Essa experiência é possível por meio de dispositivos especializados com um botão PTT dedicado.

- **Auriculares**
  - Headsets sem fio (iOS & Android)
    - [BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie)
  - Headsets com fio (somente Android)
    - [Klein Electronics](https://www.kleinelectronics.com/poc-accessories/mtwt/)
- **Telefones Android robustos**
  - Samsung [Galaxy XCover Pro](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/), [Galaxy XCover 5](https://www.samsung.com/de/smartphones/others/galaxy-xcover-5-black-64gb-sm-g525fzkdeeb/buy), [Galaxy Tab Active 3](https://www.samsung.com/us/business/tablets/galaxy-tab-active/buy/)
    - Configuração manual – Com o Teams instalado, navegue até Configurações > recursos avançados > chave XCover/Active. Ativar 'Controlar chave XCover com aplicativo' e selecionar 'Teams'
    - [Configuração do MDM](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)
  - Zebra [TC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc52-tc57-series-touch-computer.html), [TC7x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc72-tc77-series-touch-computer.html), [TC2x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc21-tc26.html), [EC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec50-ec55.html), [EC30](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec30.html), [MC3300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc3300.html), [MC9300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc9300.html) 
    - Configuração manual – Com o Teams instalado, o botão PTT dedicado (LEFT_TRIGGER_2) funciona com o Walkie Talkie por padrão
    
> [!NOTE]
> Esses dispositivos não são certificados pelo Teams. Eles foram validados para trabalhar com o Walkie Talkie do Teams.

### <a name="license-requirements"></a>Requisitos de licença

O aplicativo Walkie Talkie está incluído em todas as licenças pagas do Teams [Office 365 assinaturas](/office365/servicedescriptions/teams-service-description). Para obter mais informações sobre como obter o Teams, confira [Como fazer obter acesso ao Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)?

## <a name="further-information"></a>Mais informações

- Os administradores de TI podem manter o controle sobre quem está usando o Walkie Talkie por meio de políticas de aplicativo.
- Se o trabalhador da linha de frente estiver usando dados móveis para se comunicar por meio do Teams, o Walkie Talkie usará o mesmo método.
- Walkie Talkie deve funcionar bem em situações de baixa largura de banda ou situações em que seu smartphone está conectado e funcionando. Walkie Talkie não funcionará quando não houver nenhuma conectividade.

Para obter mais leituras sobre a experiência do usuário final, consulte:

- [Introdução ao Walkie Talkie do Teams](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [Comunicar-se com sua equipe com o Walkie Talkie](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
