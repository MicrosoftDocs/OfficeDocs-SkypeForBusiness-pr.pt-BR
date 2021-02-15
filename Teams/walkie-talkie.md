---
title: Aplicativo Walkie Talkie no Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Como configurar o aplicativo Walkie Talkie no Microsoft Teams, de uma perspectiva itadmin.
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
ms.openlocfilehash: 63cd853b8a068e7acfc5752e3cd94b5d0102bc2f
ms.sourcegitcommit: 04eba352d9e203aa9cd1282c4f4c7158a0469678
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2021
ms.locfileid: "49944586"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>Aplicativo Walkie Talkie no Microsoft Teams

O aplicativo Walkie Talkie no Teams fornece comunicação por push-to-talk (PTT) instantânea para sua equipe e agora está disponível no Android. O Walkie Talkie permite que os usuários se conectem com sua equipe usando os mesmos canais subjacentes dos que são membros. Somente os usuários que se conectam ao Walkie Talkie em um canal se tornam participantes e podem se comunicar uns com os outros usando o push-to-talk, um de cada vez.

Com o Walkie Talkie no Teams, os trabalhadores da linha de frente agora podem se comunicar com segurança com uma experiência de PTT familiar sem precisar carregar rádios em massa, e o Walkie Talkie funciona em qualquer lugar com WiFi ou conectividade com a Internet celular.

## <a name="getting-started"></a>Introdução

### <a name="deploying-walkie-talkie"></a>Implantando o Walkie Talkie

Atualmente, o Walkie Talkie não está pré-instalado. Para habilitar esse recurso para os usuários em sua [](teams-app-setup-policies.md)organização, você precisa adicionar Walkie Talkie à Política de Configuração de Aplicativo atribuída aos usuários do Centro de   Administração do [Teams.](https://admin.teams.microsoft.com/)

Depois de habilitado, o Walkie Talkie ficará disponível no aplicativo Android dentro de 48 horas.

### <a name="adding-walkie-talkie-to-your-app-list"></a>Adicionar Walkie Talkie à sua lista de aplicativos

No Centro de administração do Microsoft Teams, em políticas de configuração de aplicativos do **Teams,** você deve ter Permitir que o  >   **pinamento do usuário** seja definido como **Em.** Em seguida, na seção Aplicativos Fixados, clique **em +Adicionar Aplicativos.**

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="Mostra a seção Aplicativos Fixados e o botão Adicionar Aplicativos a ser selecionado.":::

No painel **Adicionar aplicativos fixados** que  aparece à direita, use a caixa de texto Pesquisar para procurar o Walkie Talkie. Quando você o tiver como resultado de pesquisa, clique no **botão** Adicionar à direita do nome para adicioná-lo à sua lista.

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Mostra a barra lateral Adicionar aplicativos fixados com o Walkie inserido no painel de pesquisa e o aplicativo Walkie Talkie nos resultados da pesquisa, com o botão Adicionar ao lado dele.":::

O aplicativo Walkie Talkie agora deve aparecer na lista Aplicativos Fixados e estará disponível para uso depois que você clicar no **botão** Salvar.

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="Mostra a lista de aplicativos fixados com o aplicativo Walkie Talkie adicionado e o botão Salvar abaixo da lista.":::

### <a name="network-documentation"></a>Documentação de rede

O Walkie Talkie no Teams requer conectividade com a Internet e, abaixo das condições de rede, são necessários para uma experiência ideal.

|Indicador | Obrigatório |
|---|---|
|Latência (RTT) | < 300ms |
|Tremulação |< 30ms |
|Perda de pacote |< 1% |

Conforme mencionado acima, a qualidade da mídia em tempo real em uma rede IP é muito impactada pela qualidade da conectividade de rede, mas especialmente pela quantidade de:

- **Latência** – este é o tempo necessário para obter um pacote IP do ponto A ao ponto B na rede. Esse atraso de propagação de rede está essencialmente ligado à distância física entre os dois pontos e a velocidade da luz, incluindo a sobrecarga adicional sofrida pelos vários roteadores intermediários. A latência é medida como RTT (Tempo de Ida e Volta).
- **Perda de** pacote – isso geralmente é definido como uma porcentagem de pacotes que são perdidos em um determinado período de tempo. A perda de pacote afeta diretamente a qualidade do áudio, desde pacotes perdidos pequenos e individuais que quase não têm impacto, até perdas de estouro de retorno para trás que causam corte total do áudio.
- **Jitter** - Essa é a alteração média de atraso entre pacotes sucessivos.

O uso esperado de dados do Walkie Talkie é de cerca de 20KB/s ao enviar ou receber áudio. Quando ocioso, o uso esperado de dados do Walkie Talkie é negligível.

### <a name="walkie-talkie-devices"></a>Dispositivos Walkie Talkie

Os trabalhadores da linha de frente geralmente precisam falar e receber chamadas do Walkie Talkie mesmo quando seus telefones estão bloqueados. Essa experiência é possível por meio de dispositivos especializados com um botão PTT dedicado.

- Auriculares
  - Fones de ouvido com fio ([Electronics Electronics)](https://www.kleinelectronics.com/poc-accessories/mtwt/)
  - Fones de ouvido sem fio[(Jabra BlueParrott)](https://www.blueparrott.com/microsoft-teams-walkie-talkie)
- Telefones robustos
  - Samsung Galaxy XCover Pro
    - [Mais informações.](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/)
    - [Guia de configuração.](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)

> [!NOTE]
> Esses dispositivos não são certificados do Teams. Eles foram validados para trabalhar com o Walkie Talkie do Teams.

### <a name="license-requirements"></a>Requisitos de licença

O aplicativo Walkie Talkie está incluído em todas as licenças pagas do Teams nas [assinaturas do Office 365.](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing) Para obter mais informações sobre como obter o Teams, confira [Como obter acesso ao Microsoft Teams?](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

> [!NOTE]
> Determinados recursos avançados podem exigir licenciamento adicional. Por exemplo, a integração com o Samsung Galaxy XCover Pro requer uma licença do Knox.

## <a name="further-information"></a>Mais informações

- O ITAdmins pode manter o controle sobre quem está usando o Walkie Talkie por meio de Políticas de Aplicativos.
- Se o seu trabalhador da linha de frente estiver usando dados móveis para se comunicar por meio do Teams, Walkie Talkie usará o mesmo método.
- O Walkie Talkie deve funcionar bem em situações de baixa largura de banda ou situações em que seu smartphone está conectado e funcionando. Walkie Talkie não funcionará quando não houver conectividade.

Para saber mais sobre a experiência do usuário final, consulte:

- [Começar a trabalhar com o Walkie Talkie do Teams](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [Comunique-se com sua equipe com Walkie Talkie](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
