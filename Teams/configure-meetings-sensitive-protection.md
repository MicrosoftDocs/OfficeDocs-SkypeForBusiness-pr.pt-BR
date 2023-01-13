---
title: Configurar reuniões do Teams com proteção para dados confidenciais
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
audience: admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- m365solution-compliantmeetings
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
description: Saiba como configurar reuniões do Teams para proteção de informações confidenciais usando modelos e rótulos de confidencialidade.
ms.openlocfilehash: 3aae927f29464f3e5d8a9e695c170ded06d3dd1f
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800094"
---
# <a name="configure-teams-meetings-with-protection-for-sensitive-data"></a>Configurar reuniões do Teams com proteção para dados confidenciais

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

Para o nível *sensível* de proteção, vamos restringir quem pode ignorar o lobby, quem pode apresentar e quem pode gravar. Você também pode restringir ações adicionais se sua organização exigir isso.

A tabela a seguir descreve quais ações restringiremos para reuniões confidenciais e onde essas configurações estão configuradas.

|Recurso|Configuração|Localização|Aplicada|
|:------|:------|:-------|:-------|
|Permitir câmera para participantes|**Ativado**|Modelo|Não|
|Permitir microfone para participantes|**Ativado**|Modelo|Não|
|Aplicar uma marca d'água ao feed de vídeo de todos|**Desativado**|Modelo|Não|
|Aplicar uma marca d'água ao conteúdo compartilhado|**Desativado**|Modelo|Não|
|Criptografia de ponta a ponta|**Desativado**|Modelo|Não|
|Gerenciar o que os participantes veem|**Ativado**|Modelo|Não|
|Chat de reunião|**Ativado**|Modelo|Não|
|Pessoas discagem pode ignorar o lobby|**Desativado**|Modelo|Sim|
|Impedir a cópia do conteúdo do chat na área de transferência|**Desativado**|Rótulo|Não|
|Gravar automaticamente|**Desativado**|Modelo|Não|
|Quem pode ignorar o lobby|**Somente pessoas que foram convidadas**|Rótulo|Sim|
|Quem pode apresentar|**Pessoas na minha organização e convidados**|Rótulo|Sim|
|Quem pode gravar|**Organizadores e co-organizadores**|Rótulo|Sim|

As configurações listadas como impostas são impostas pelo rótulo de confidencialidade ou pelo modelo de reunião. As configurações que não são impostas podem ser alteradas pelo organizador da reunião.

> [!Note]
> As configurações de reunião em rótulos de confidencialidade e modelos de reunião personalizados exigem Teams Premium.

## <a name="presentation-options-for-sensitive-meetings"></a>Opções de apresentação para reuniões confidenciais

Para o nível *sensível* de proteção, estamos aplicando configurações específicas para quem pode apresentar, bem como como o conteúdo é compartilhado.

Ao **ativar Gerenciar o que os participantes podem ver**, garantimos que os organizadores da reunião possam examinar o conteúdo compartilhado antes que ele seja colocado na tela para os participantes. Neste exemplo, estamos usando um modelo para ativar isso por padrão, mas você também pode aplicá-lo no modelo, se necessário.

Ao definir **Quem pode apresentar** **para Pessoas na minha organização e convidados** no rótulo de confidencialidade, removemos a chance de participantes anônimos apresentarem na reunião. Você pode restringir ainda mais isso a **apenas organizadores e co-organizadores** , se necessário. (Faremos isso para o nível *altamente sensível* de proteção.)

Também restringiremos a gravação aos organizadores e co-organizadores usando o rótulo de confidencialidade.

## <a name="lobby-options-for-sensitive-meetings"></a>Opções de lobby para reuniões confidenciais

Usaremos o rótulo de confidencialidade para impedir que qualquer pessoa que não seja participante convidado (pessoas diretamente convidadas pelo organizador ou para quem um convite foi encaminhado) ignore o lobby. Isso dá um nível extra de proteção, permitindo que o organizador vete alguém que não enviou diretamente um convite antes de admiti-los na reunião. Você pode restringir ainda mais essa configuração escolhendo **somente organizadores e co-organizadores**. (Faremos isso para o nível *altamente sensível* de proteção.)


## <a name="sensitivity-labels"></a>Rótulos de confidencialidade

Para o nível sensível de proteção, usaremos um rótulo de confidencialidade que você pode usar diretamente em uma reunião ou como parte de um modelo de reunião. Dependendo da configuração escolhida, esse rótulo também pode ser usado para classificar equipes e arquivos individuais.

Se você já tiver rótulos de confidencialidade implantados em sua organização, considere como esse rótulo se encaixa com sua estratégia geral de rótulo. Você pode alterar o nome ou as configurações, se necessário, para atender às necessidades da sua organização. Se você já tiver um rótulo que usa para obter informações confidenciais, poderá editar o rótulo e adicionar reuniões do Teams a ele.

Para criar um rótulo de confidencialidade
1. Abra o [portal de conformidade do Microsoft Purview](https://compliance.microsoft.com).
1. Em **Soluções**, clique em **Proteção de informações**.
1. Clique **em Criar um rótulo**.
1. Dê um nome ao rótulo. Sugerimos **Confidencial**, mas você pode escolher um nome diferente se esse já estiver em uso.
1. Adicione um nome de exibição e uma descrição e clique em **Avançar**.
1. Na página **Definir o escopo para este rótulo** , selecione **Itens** e **Incluir reuniões**. (Observe que você pode selecionar outras opções se quiser usar esse rótulo para outras finalidades.)
1. Selecione **Avançar**.
1. Continue selecionando as opções que você deseja usar com este rótulo e, em seguida, na página **Configurações para reuniões e chats do Teams** , escolha os seguintes valores:
    1. Selecione **Controle que pode ignorar o lobby** e escolha **Somente pessoas que foram convidadas** na lista suspensa.
    1. Selecione **Controlar quem pode apresentar** e escolher **Pessoas na minha organização e convidados** na lista suspensa.
    1. Selecione **Quem pode gravar** e escolher **Organizadores e co-organizadores** na lista suspensa.
    1. Configure quaisquer outras configurações necessárias para sua organização.
    <!--:::image type="content" source="media/teams-meeting-sensitivity-label-sensitive-small.png" alt-text="Screenshot of sensitivity label meeting settings." lightbox="media/teams-meeting-sensitivity-label-sensitive-large.png":::-->
1. Selecione **Avançar**.
1. Conclua o assistente com as configurações adicionais que você deseja usar e selecione **Criar rótulo** e selecione **Concluído**.

Depois de criar o rótulo, você precisará publicá-lo para os usuários que o usarão. Para proteção confidencial, disponibilizaremos o rótulo para todos os usuários. Você publica o rótulo no portal de conformidade do Microsoft Purview, na guia **Políticas** de rótulo da página **Proteção de informações**. Se você tiver uma política existente que se aplique a todos os usuários, adicione esse rótulo a essa política. Se você precisar criar uma nova política, consulte [Publicar rótulos de confidencialidade criando uma política de rótulo](/compliance/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy).

Para obter informações adicionais sobre como usar rótulos de confidencialidade com reuniões, consulte [Usar rótulos de confidencialidade para proteger itens de calendário, reuniões do Teams e chat](/microsoft-365/compliance/sensitivity-labels-meetings).

## <a name="meeting-templates"></a>Modelos de reunião

Uma vantagem de usar modelos é que você pode criar vários modelos que usam o mesmo rótulo de confidencialidade que bloqueiam configurações diferentes. Por exemplo, se algumas de suas reuniões confidenciais forem apresentações em que há uma interação mínima dos participantes, você poderá criar um modelo que desative o vídeo do participante e até mesmo o chat, e outro modelo que deixe essas opções para o organizador da reunião. Ambos os modelos usariam o rótulo *Sensitive* .

No nível *sensível* de proteção, usaremos o modelo para impedir que as pessoas discando por telefone ignorem o lobby. Se houver certos tipos de reuniões em que você deseja permitir que as pessoas que ligam por telefone ignorem o lobby, considere usar um modelo separado com o mesmo rótulo para essas reuniões.

Para criar um modelo de reunião personalizado

1. No centro de administração do Teams, expanda **Reuniões** e selecione **Modelos de reunião**.
1. Selecione **Adicionar**
1. Digite um nome e uma descrição para o modelo.
1. Na seção **Aplicar rótulo de confidencialidade** , escolha o rótulo que você criou acima.
1. Selecione **Aplicar rótulo de confidencialidade** e selecione **Bloquear**.
1. Verifique se **Pessoas ligação no meu telefone pode ignorar se o lobby** está definido como **Desativado**, selecione-o e selecione **Bloquear**.
1. Altere as configurações adicionais, se desejar.
1. Para impedir que o organizador da reunião altere uma configuração, selecione a configuração e selecione **bloquear**.
1. Para impedir que o organizador da reunião veja uma configuração, selecione a configuração e selecione **Ocultar**.
1. Selecione **Salvar**.

## <a name="related-topics"></a>Tópicos relacionados

[Configurar reuniões do Teams com três camadas de proteção](configure-meetings-three-tiers-protection.md)

[Visão geral dos modelos de reunião personalizados no Microsoft Teams](custom-meeting-templates-overview.md)

[Use modelos de reunião do Teams, rótulos de confidencialidade e políticas de administrador juntos para reuniões confidenciais](meeting-templates-sensitivity-labels-policies.md)
