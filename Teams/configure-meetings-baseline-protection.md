---
title: Configurar reuniões do Teams com proteção de linha de base
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
description: Saiba como configurar reuniões do Teams para um nível de proteção de linha de base usando modelos e rótulos de confidencialidade.
ms.openlocfilehash: 3770bb03c1986c4a6bbef72408340fd791b058f1
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800105"
---
# <a name="configure-teams-meetings-with-baseline-protection"></a>Configurar reuniões do Teams com proteção de linha de base

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

Para o nível de linha de *base* de proteção, vamos restringir quem pode ignorar o lobby usando um rótulo de confidencialidade e definir um valor padrão para quem pode apresentar uma política de administrador do Teams. Você também pode restringir ações adicionais se sua organização exigir isso.

> [!Note]
> As configurações de reunião em rótulos de confidencialidade e modelos de reunião personalizados exigem Teams Premium.

A tabela a seguir descreve quais ações restringiremos para reuniões de linha de base e onde essas configurações estão configuradas.

|Recurso|Configuração|Localização|Aplicada|
|:------|:------|:-------|:-------|
|Permitir câmera para participantes|**Ativado**|Modelo|Não|
|Permitir microfone para participantes|**Ativado**|Modelo|Não|
|Aplicar uma marca d'água ao feed de vídeo de todos|**Desativado**|Rótulo|Sim|
|Aplicar uma marca d'água ao conteúdo compartilhado|**Desativado**|Rótulo|Sim|
|Criptografia de ponta a ponta|**Desativado**|Rótulo|Sim|
|Gerenciar o que os participantes veem|**Desativado**|Modelo|Não|
|Chat de reunião|**Ativado**|Modelo|Não|
|Pessoas discagem pode ignorar o lobby|**Desativado**|Modelo|Sim|
|Impedir a cópia do conteúdo do chat na área de transferência|**Desativado**|Rótulo|Sim|
|Gravar automaticamente|**Desativado**|Modelo|Não|
|Quem pode ignorar o lobby|**Pessoas na minha organização, pessoas em organizações confiáveis e convidados**|Modelo|Não|
|Quem pode apresentar|**Todos na organização, mas o usuário pode substituir**|Centro de administração do Teams|Não|
|Quem pode gravar|**Organizadores e apresentadores**|Modelo|Não|

As configurações listadas como impostas são impostas pelo rótulo de confidencialidade ou pelo modelo de reunião. As configurações que não são impostas podem ser alteradas pelo organizador da reunião.

## <a name="default-values-for-who-can-present"></a>Valores padrão para **Quem pode apresentar**

O valor padrão para **Quem pode apresentar** é **Todos**. Para a camada de proteção de linha de base, definiremos um padrão mais seguro de **Todos na organização, que os** organizadores da reunião podem mudar se desejarem.

Podemos definir esse valor com um rótulo de confidencialidade, mas o valor será imposto para todas as reuniões com esse rótulo. Essa configuração não está disponível em modelos de reunião, portanto, vamos defini-la no centro de administração do Teams.

Para configurar quem pode apresentar em reuniões
1. No centro de administração do Teams, expanda **Reuniões** e selecione **Políticas de reunião**.
1. Selecione a política que você deseja atualizar.
1. Em **Participantes & convidados**, defina **Quem pode apresentar em reuniões** para **Todos na organização, mas o usuário pode substituir**.
1. Selecione **Salvar**.

## <a name="watermarks-and-end-to-end-encryption"></a>Marcas d'água e criptografia de ponta a ponta

No nível de *linha de base* de proteção, desabilitaremos marcas d'água e criptografia de ponta a ponta usando um rótulo de confidencialidade. Isso impedirá que os organizadores da reunião usem esses recursos. Marcas d'água e criptografia de ponta a ponta são mais aplicáveis a reuniões confidenciais.

Criptografia de ponta a ponta e marcas d'água desabilitam alguns outros recursos, como gravação de reunião. Desativar para o nível de *linha de base* de proteção pode evitar instâncias em que os organizadores da reunião usam esses recursos sem perceber os limites impostos.

Se você trabalha em uma indústria altamente regulamentada, talvez queira manter esses recursos disponíveis mesmo no nível de linha de *base* de proteção.

## <a name="sensitivity-labels"></a>Rótulos de confidencialidade

Para o nível de *linha de base* de proteção, usaremos um rótulo de confidencialidade que você pode usar diretamente em uma reunião ou como parte de um modelo de reunião. Dependendo da configuração escolhida, esse rótulo também pode ser usado para classificar equipes e arquivos individuais.

Se você já tiver rótulos de confidencialidade implantados em sua organização, considere como esse rótulo se encaixa com sua estratégia geral de rótulo. Você pode alterar o nome ou as configurações mostradas abaixo, se necessário, para atender às necessidades da sua organização. Se você já tiver um rótulo usado para a linha de base ou proteção geral, poderá editar o rótulo e adicionar reuniões do Teams a ele.

Para criar um rótulo de confidencialidade
1. Abra o [portal de conformidade do Microsoft Purview](https://compliance.microsoft.com).
1. Em **Soluções**, clique em **Proteção de informações**.
1. Clique **em Criar um rótulo**.
1. Dê um nome ao rótulo. Sugerimos **Confidencial**, mas você pode escolher um nome diferente se esse já estiver em uso.
1. Adicione um nome de exibição e uma descrição e clique em **Avançar**.
1. Na página **Definir o escopo para este rótulo** , selecione **Itens** e **Incluir reuniões**. (Observe que você pode selecionar outras opções se quiser usar esse rótulo para outras finalidades.)
1. Selecione **Avançar**.
1. Continue selecionando as opções que você deseja usar com este rótulo e, em seguida, na página **Configurações para reuniões e chats do Teams** , escolha os seguintes valores:
    1. Selecione **Controlar criptografia de ponta a ponta para vídeo e áudio de reunião** e defina **Aplicar criptografia de ponta a ponta** como **Desativada**.
    1. Selecione **Controlar marcas d'água** e defina **Aplicar marcas d'água ao conteúdo compartilhado** e **Aplicar marcas d'água ao feed de vídeo de todos** para **Desativar**.
    1. Configure quaisquer outras configurações necessárias para sua organização.
    <!--:::image type="content" source="media/teams-meeting-sensitivity-label-baseline-small.png" alt-text="Screenshot of sensitivity label meeting settings." lightbox="media/teams-meeting-sensitivity-label-baseline-large.png":::-->
1. Selecione **Avançar**.
1. Conclua o assistente com as configurações adicionais que você deseja usar e selecione **Criar rótulo** e selecione **Concluído**.

Depois de criar o rótulo, você precisará publicá-lo para os usuários que o usarão. Para proteção de linha de base, disponibilizaremos o rótulo para todos os usuários. Você publica o rótulo no portal de conformidade do Microsoft Purview, na guia **Políticas** de rótulo da página **Proteção de informações**. Se você tiver uma política existente que se aplique a todos os usuários, adicione esse rótulo a essa política. Se você precisar criar uma nova política, consulte [Publicar rótulos de confidencialidade criando uma política de rótulo](/compliance/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy).

Para obter informações adicionais sobre como usar rótulos de confidencialidade com reuniões, consulte [Usar rótulos de confidencialidade para proteger itens de calendário, reuniões do Teams e chat](/microsoft-365/compliance/sensitivity-labels-meetings).

## <a name="meeting-templates"></a>Modelos de reunião

No nível de *linha de base* de proteção, usaremos o modelo para definir um valor padrão para quem pode ignorar o lobby que inclui participantes externos de domínios confiáveis.

Também impediremos que as pessoas discando por telefone ignorem o lobby. Você pode omitir essa configuração se sua organização realizar reuniões com frequência em que os participantes discados devem ser capazes de ingressar diretamente. Se houver determinados tipos de reuniões em que isso seja verdadeiro, considere usar um modelo separado para essas reuniões.

Se você tiver escolhido desabilitar marcas d'água e criptografia de ponta a ponta na confidencialidade, também poderá usar o modelo para ocultar essas configurações do organizador da reunião.

Para criar um modelo de reunião personalizado

1. No centro de administração do Teams, expanda **Reuniões** e selecione **Modelos de reunião**.
1. Selecione **Adicionar**
1. Digite um nome e uma descrição para o modelo.
1. Na seção **Aplicar rótulo de confidencialidade** , escolha o rótulo que você criou acima.
1. Selecione **Aplicar rótulo de confidencialidade** e selecione **Bloquear**.
1. Na lista suspensa Do **Lobby** , selecione **Todos na minha organização, organizações confiáveis e convidados**.
1. Verifique se **Pessoas ligação no meu telefone pode ignorar se o lobby** está definido como **Desativado**, selecione-o e selecione **Bloquear**.
1. Se você desabilitou marcas d'água e criptografia de ponta a ponta com o rótulo de confidencialidade, considere selecionar essas configurações aqui e selecionar **Ocultar** para que os organizadores da reunião não as vejam.
1. Altere as configurações adicionais, se desejar.
1. Para impedir que o organizador da reunião altere uma configuração, selecione a configuração e selecione **bloquear**.
1. Para impedir que o organizador da reunião veja uma configuração, selecione a configuração e selecione **Ocultar**.
1. Selecione **Salvar**.

## <a name="related-topics"></a>Tópicos relacionados

[Configurar reuniões do Teams com três camadas de proteção](configure-meetings-three-tiers-protection.md)

[Visão geral dos modelos de reunião personalizados no Microsoft Teams](custom-meeting-templates-overview.md)

[Use modelos de reunião do Teams, rótulos de confidencialidade e políticas de administrador juntos para reuniões confidenciais](meeting-templates-sensitivity-labels-policies.md)
