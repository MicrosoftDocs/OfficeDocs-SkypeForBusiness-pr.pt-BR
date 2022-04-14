---
title: Aplicativo Walkie Talkie no Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
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
ms.openlocfilehash: c19894106dfd06c13ec9936657837aa42fcdade0
ms.sourcegitcommit: 480046a53dfb6e6cf867e1920f8fb43dda9d3774
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2022
ms.locfileid: "62015011"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>Aplicativo Walkie Talkie no Microsoft Teams

O aplicativo Walkie Talkie no Teams fornece comunicação instantânea por push-to-talk (PTT) para sua equipe e agora está disponível no Android & iOS. O Walkie Talkie permite que os usuários se conectem com sua equipe usando os mesmos canais subjacentes dos quais são membros. Somente os usuários que se conectam ao Walkie Talkie em um canal se tornam participantes e podem se comunicar entre si usando o push-to-talk, um de cada vez.

Com o Walkie Talkie no Teams, os trabalhadores da linha de frente agora podem se comunicar com segurança com uma experiência de PTT familiar sem a necessidade de transportar rádios em massa, e Walkie Talkie trabalha em qualquer lugar com conectividade wi-fi ou de internet celular.

## <a name="getting-started"></a>Introdução

### <a name="deploying-walkie-talkie"></a>Implantando Walkie Talkie

O Walkie Talkie tem suporte em dispositivos Android com o Google Serviços Móveis (GMS) e dispositivos iOS. 

Atualmente, o Walkie Talkie não está pré-instalado. Para habilitar esse recurso para usuários em sua organização, você precisa adicionar o Walkie Talkie à Política de Configuração do  [Aplicativo](teams-app-setup-policies.md)  atribuída aos usuários do [Centro de Administração do Teams.](https://admin.teams.microsoft.com/) Depois de habilitado, o Walkie Talkie ficará disponível no aplicativo dentro de 48 horas.

### <a name="adding-walkie-talkie-to-your-app-list"></a>Adicionando o Walkie Talkie à sua lista de aplicativos

No centro Microsoft Teams de administração, em Teams **políticas** **appSetup** > , você deve ter Permitir fixação **de** usuário definida como **Ativado**. Em seguida, na seção Aplicativos Fixados, clique **em +Adicionar Aplicativos**.

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="Mostra a seção Aplicativos Fixados e o botão Adicionar Aplicativos a serem selecionados.":::

No painel **Adicionar aplicativos** fixados que aparece à direita, use a  caixa de texto Pesquisar para procurar o Walkie Talkie. Quando você o tiver como resultado da pesquisa, selecione o  botão Adicionar à direita do nome para adicioná-lo à sua lista.

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Mostra a barra lateral Adicionar aplicativos fixados com Walkie inserido no painel de pesquisa e o aplicativo Walkie Talkie nos resultados da pesquisa, com o botão Adicionar ao lado dele.":::

O aplicativo Walkie Talkie agora deve aparecer na lista aplicativos fixados e estar disponível para uso depois que você clicar no **botão** Salvar.

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="Mostra a lista de aplicativos fixados com o aplicativo Walkie Talkie adicionado e o botão Salvar abaixo da lista.":::

### <a name="network-documentation"></a>Documentação da rede

O Walkie Talkie no Teams requer conectividade com a Internet e, abaixo das condições de rede, são necessários para uma experiência ideal.

|Indicador | Obrigatório |
|---|---|
|Latência (RTT) | < 300 ms |
|Tremulação |< 30 ms |
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
    - Configuração manual – com Teams instalada, navegue até Configurações > recursos avançados > chave XCover/Active. Ativar 'Controlar chave XCover com aplicativo' e selecionar 'Teams'
    - [Configuração do MDM](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)
  - Zebra [TC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc52-tc57-series-touch-computer.html), [TC7x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc72-tc77-series-touch-computer.html), [TC2x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc21-tc26.html), [EC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec50-ec55.html), [EC30](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec30.html), [MC3300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc3300.html), [MC9300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc9300.html) 
    - Configuração manual – com Teams instalado, o botão PTT dedicado (LEFT_TRIGGER_2) funciona com o Walkie Talkie por padrão
    
> [!NOTE]
> Esses dispositivos não são Teams certificados. Eles foram validados para trabalhar com Teams Walkie Talkie.

### <a name="license-requirements"></a>Requisitos de licença

O aplicativo Walkie Talkie está incluído em todas as licenças pagas Teams em [Office 365 assinaturas](/office365/servicedescriptions/teams-service-description). Para obter mais informações sobre como Teams, confira  [Como fazer obter acesso ao Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)?

## <a name="further-information"></a>Mais informações

- O ITAdmins pode manter o controle sobre quem está usando o Walkie Talkie por meio de Políticas de Aplicativo.
- Se o trabalhador da linha de frente estiver usando dados móveis para se comunicar Teams, o Walkie Talkie usará o mesmo método.
- Walkie Talkie deve funcionar bem em situações de baixa largura de banda ou situações em que seu smartphone está conectado e funcionando. O Walkie Talkie não funcionará quando não houver nenhuma conectividade.

Para obter mais leituras sobre a experiência do usuário final, consulte:

- [Introdução com Teams Walkie Talkie](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [Comunicar-se com sua equipe com o Walkie Talkie](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
