---
title: Aplicativo Walkie Talkie no Microsoft Teams
author: LanaChin
ms.author: v-lanachin
manager: samanro
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Como configurar o aplicativo Walkie Talkie no Microsoft Teams, de uma perspectiva de administrador de TI.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365-frontline
- tier2
- highpri
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.date: 11/17/2022
ms.openlocfilehash: abb14f937064b394106e0cf2d58f756371a7c04e
ms.sourcegitcommit: ff161779577ce9cc892f1b6b8861ad49ff4c3ca3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2022
ms.locfileid: "69131270"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>Aplicativo Walkie Talkie no Microsoft Teams

O aplicativo Walkie Talkie no Teams fornece comunicação PTT (push-to-talk) instantânea para sua equipe e está disponível no Android e iOS. O Walkie Talkie permite que os usuários se conectem com sua equipe usando os mesmos canais subjacentes dos quais são membros.

Somente usuários que se conectam ao Walkie Talkie em um canal se tornam participantes e podem se comunicar entre si usando ptt. Os usuários continuarão a receber transmissões até tocarem em  **Desconectar**.

Com o Walkie Talkie no Teams, os usuários podem se comunicar com segurança com uma experiência PTT familiar sem precisar carregar rádios volumosos, e o Walkie Talkie funciona em qualquer lugar com conectividade WiFi ou internet celular.

> [!NOTE]
> Walkie Talkie atualmente não está disponível na China.

## <a name="license-requirements"></a>Requisitos de licença

O Walkie Talkie está incluído em todas as licenças pagas do Teams nas [assinaturas do Microsoft 365 e Office 365](/office365/servicedescriptions/teams-service-description). Para obter mais informações sobre como obter o Teams, confira [Como fazer obter o Microsoft Teams?](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

## <a name="deploying-walkie-talkie"></a>Implantando o Walkie Talkie

Há suporte para o Walkie Talkie em dispositivos Android com o GMS (Serviços Móveis do Google) e dispositivos iOS.

### <a name="step-1-make-sure-walkie-talkie-is-enabled-in-your-organization"></a>Etapa 1: verifique se o Walkie Talkie está habilitado em sua organização

Por padrão, o aplicativo Walkie Talkie está habilitado para todos os usuários do Teams em sua organização.

Você controla se o aplicativo está disponível no nível da organização na página [Gerenciar aplicativos](manage-apps.md) no centro de administração do Microsoft Teams. Para confirmar se o aplicativo está habilitado em sua organização:

1. Na navegação à esquerda do centro de administração do Teams, acesse **Aplicativos do Teams** > **Gerenciar aplicativos**.
2. Na lista de aplicativos, pesquise o aplicativo Walkie Talkie, selecione-o e verifique se o alternância **status** está definido como **Permitido**.

Se você quiser permitir ou bloquear usuários específicos em sua organização de usar o Walkie Talkie, verifique se o Walkie Talkie está habilitado para sua organização na página [Gerenciar aplicativos](manage-apps.md) . Em seguida, crie uma política personalizada para permissões de aplicativo e atribua-a a esses usuários. Para saber mais, confira [Gerenciar políticas de permissão de aplicativos no Teams](teams-app-permission-policies.md).

### <a name="step-2-pin-walkie-talkie-to-teams"></a>Etapa 2: Fixar Walkie Talkie no Teams

#### <a name="use-the-tailored-frontline-app-experience-to-pin-walkie-talkie-and-other-apps-to-teams"></a>Usar a experiência de aplicativo de linha de frente personalizada para fixar o Walkie Talkie e outros aplicativos no Teams

A experiência de aplicativo de linha de frente personalizada no Teams fixa os aplicativos mais relevantes no Teams para usuários que têm uma [licença F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt). Os aplicativos fixados incluem Walkie Talkie, Shifts, Tarefas e Aprovações. Por padrão, esse recurso está ativado, dando aos seus trabalhadores de linha de frente uma experiência fora da caixa que é adaptada às suas necessidades.

Os aplicativos são fixados na bandeja de aplicativos na parte inferior dos clientes móveis do Teams, onde os usuários podem acessá-los de forma rápida e fácil.

Para saber mais, incluindo como a experiência funciona com políticas de aplicativo definidas, confira [Adaptar aplicativos do Teams para seus trabalhadores de linha de frente](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json).

#### <a name="use-an-app-setup-policy-to-pin-walkie-talkie-to-teams"></a>Usar uma política de configuração de aplicativo para fixar o Walkie Talkie no Teams

As políticas de configuração do aplicativo permitem personalizar o Teams para fixar aplicativos que são mais importantes para seus usuários em seus usuários.

Para fixar o aplicativo Walkie Talkie para seus usuários, você pode editar a política global (padrão em toda a organização) ou criar e atribuir uma política personalizada na política de configuração do aplicativo. Para saber mais, confira [Gerenciar políticas de configuração de aplicativos no Teams](teams-app-setup-policies.md).

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Captura de tela mostrando a adição do Walkie Talkie à lista de aplicativos fixados no painel Adicionar aplicativos fixados." lightbox="media/deploy-walkie-talkie-2.png":::

## <a name="network-documentation"></a>Documentação de rede

O Walkie Talkie no Teams requer conectividade com a Internet. As condições de rede a seguir são necessárias para uma experiência ideal.

|Indicador | Obrigatório |
|---|---|
|Latência (RTT) | < 300 ms |
|Tremulação |< 30 ms |
|Perda de pacote |< 1% |

Conforme observado acima, a qualidade da mídia em tempo real em uma rede IP é muito afetada pela qualidade da conectividade de rede, mas especialmente pela quantidade de:

- **Latência** – O tempo necessário para obter um pacote IP do ponto A para o ponto B na rede. Esse atraso de propagação de rede está essencialmente ligado à distância física entre os dois pontos e a velocidade da luz, incluindo mais sobrecarga tomada pelos vários roteadores no meio. A latência é medida como RTT (Tempo de viagem de ida e volta).
- **Nervosismo entre chegadas** – A alteração média de atraso entre pacotes sucessivos.
- **Perda de pacote** – A perda de pacotes geralmente é definida como uma porcentagem de pacotes que são perdidos em uma determinada janela de tempo. A perda de pacote afeta diretamente a qualidade do áudio , de pacotes pequenos e individuais perdidos que quase não têm impacto, a perdas de estouro consecutivas que causam um recorte completo de áudio.

O uso esperado de dados do Walkie Talkie é de cerca de 20 Kb/s ao enviar ou receber áudio. Quando ocioso, o uso esperado de dados do Walkie Talkie é insignificante.

## <a name="walkie-talkie-devices"></a>Dispositivos Walkie Talkie

Os trabalhadores da linha de frente geralmente precisam falar e receber chamadas do Walkie Talkie mesmo quando seus telefones estão bloqueados. Essa experiência é possível por meio de dispositivos especializados com um botão PTT dedicado.

#### <a name="headsets"></a>Auriculares

- Fones de ouvido sem fio (iOS e Android)
  - [BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie)
- Fones de ouvido com fio (somente Android)
  - [Klein Electronics](https://www.kleinelectronics.com/poc-accessories/mtwt/)

#### <a name="rugged-android-phones"></a>Telefones Android robustos

- Crosscall [Core-X4](https://www.crosscall.com/en_FR/core-x4-1001010801327.html), [Core-M5](https://www.crosscall.com/en_FR/core-m5-1001011101114.html), [Action-X5](https://www.crosscall.com/en_FR/action-x5-1001020701220.html), [Core-X5](https://www.crosscall.com/en_FR/core-x5-1001010701695.html) e [Core-T5](https://www.crosscall.com/en_FR/core-t5-1003011401749.html)
  - Configuração manual: com o Teams instalado, acesse **Botões de Configurações** > . No botão Dedicado (1 ou 2), selecione **Pressionar longa** e, em seguida, escolher **Aplicativo PTT**. Selecione a roda azul ao lado **de Personalizado** e selecione **Teams**.
- Kyocera [DuraForce Ultra 5G](https://kyoceramobile.com/duraforce-ultra-5g/) e [DuraSport 5G](https://kyoceramobile.com/durasport-5g/)
  - Configuração manual: com o Teams instalado, acesse **Configurações** > **chaves programáveis**. Escolha **Tecla PTT** ou **Pressione e segure** (dependendo do dispositivo) e selecione **Teams**.
- Honeywell [CT30 XP](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/ct30-xp-handheld-computer), [CT30 XP HC](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/ct30-xp-hc-mobile-computer), [CT45 XP](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/ct45-ct45-xp), [EDA51](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/scanpal-eda51-handheld-computer), [EDA52](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/eda52-handheld-computer), [EDA52 HC](https://sps.honeywell.com/gb/en/products/productivity/mobile-computers/healthcare-computers/scanpal-eda52-healthcare-mobile-computer), 
  - Configuração manual: com o Teams instalado, o botão PTT dedicado funciona com o Walkie Talkie por padrão.
- Samsung [Galaxy XCover Pro](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/), [Galaxy XCover 5](https://www.samsung.com/de/smartphones/others/galaxy-xcover-5-black-64gb-sm-g525fzkdeeb/buy), [Galaxy Tab Active 3](https://www.samsung.com/us/business/tablets/galaxy-tab-active/buy/)
  - Configuração manual: com o Teams instalado, vá para **Configurações** Recursos  > **Avançados** > **XCover/Chave Ativa**. Ative **a tecla Control XCover com o aplicativo** e selecione **Teams**.
  - [Configuração do MDM](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)
- Sonim [XP8](https://www.sonimtech.com/products/devices/xp8/)
  - Configuração manual: com o Teams instalado, vá para **Configurações** > **Chaves Programáveis**. Escolha **Selecionar aplicativo PTT Key** e selecione **Teams**.
- Zebra [TC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc52-tc57-series-touch-computer.html), [TC7x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc72-tc77-series-touch-computer.html), [TC2x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc21-tc26.html), [EC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec50-ec55.html), [EC30](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec30.html), [MC3300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc3300.html), [MC9300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc9300.html) 
  - Configuração manual: com o Teams instalado, o botão PTT dedicado (LEFT_TRIGGER_2) funciona com o Walkie Talkie por padrão.

> [!NOTE]
> Esses dispositivos não são certificados pelo Teams. Eles foram validados para trabalhar com o Teams Walkie Talkie.

## <a name="bluetooth-devices"></a>Dispositivos Bluetooth

> [!NOTE]
> Se os usuários estiverem usando acessórios Bluetooth, verifique se a solução MDM (gerenciamento de dispositivo móvel) não bloqueia dispositivos Bluetooth.

Em dispositivos que executam o sistema operacional Android versão 12 ou posterior, as permissões Bluetooth são necessárias e as permissões de localização para se conectar usando a pilha BLE não são mais necessárias. Se "permissões próximas" não forem concedidas no nível do Teams, um usuário receberá um prompt para permissões Bluetooth. Esse prompt é exibido, se um acessório Bluetooth, como um headset, está conectado ou não ao dispositivo. Se um acessório Bluetooth estiver conectado, tocar em **Permitir** conectará o Walkie Talkie ao acessório Bluetooth.

## <a name="more-information"></a>Mais informações

- Se os usuários estiverem usando dados móveis para se comunicar via Teams, o Walkie Talkie usará o mesmo método.
- O Walkie Talkie deve funcionar bem em situações de baixa largura de banda ou em situações em que seu smartphone está conectado e funcionando. O Walkie Talkie não funcionará quando não houver conectividade.

Para saber mais sobre a experiência do usuário final, confira:

- [Introdução ao Teams Walkie Talkie](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [Comunique-se com sua equipe com o Walkie Talkie](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
