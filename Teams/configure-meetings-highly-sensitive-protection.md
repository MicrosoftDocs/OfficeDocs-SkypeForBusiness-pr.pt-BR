---
title: Configurar reuniões do Teams com proteção para dados altamente confidenciais
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
description: Saiba como configurar reuniões do Teams para proteção para informações altamente confidenciais usando modelos e rótulos de confidencialidade.
ms.openlocfilehash: 0d49cc4305f77b4b4208cc0f7418d5506155d0d6
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800259"
---
# <a name="configure-teams-meetings-with-protection-for-highly-sensitive-data"></a>Configurar reuniões do Teams com proteção para dados altamente confidenciais

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

Para o nível de proteção *altamente sensível* , examinaremos dois cenários diferentes:
- Reuniões altamente sensíveis em que os participantes participam e interagem com os apresentadores
- Apresentações altamente sensíveis em que os participantes não interagem e estão apenas exibindo a apresentação

> [!Note]
> As configurações de reunião em rótulos de confidencialidade e modelos de reunião personalizados exigem Teams Premium.

#### <a name="highly-sensitive-meetings"></a>Reuniões altamente sensíveis

Para reuniões altamente sensíveis, restringiremos quem pode ignorar o lobby, quem pode apresentar, quando os participantes puderem conversar, e bloquearemos a cópia do chat da reunião. Também habilitaremos criptografia de ponta a ponta e marca d'água para vídeo e conteúdo compartilhados. Como estamos usando marcas d'água, a gravação da reunião será desabilitada.

A tabela a seguir descreve quais ações restringiremos para reuniões altamente sensíveis e onde essas configurações estão configuradas.

|Recurso|Configuração|Localização|Aplicada|
|:------|:------|:-------|:-------|
|Permitir câmera para participantes|**Ativado**|Modelo|Não|
|Permitir microfone para participantes|**Ativado**|Modelo|Não|
|Aplicar uma marca d'água ao feed de vídeo de todos|**Ativado**|Rótulo|Sim|
|Aplicar uma marca d'água ao conteúdo compartilhado|**Ativado**|Rótulo|Sim|
|Criptografia de ponta a ponta|**Ativado**|Rótulo|Sim|
|Gerenciar o que os participantes veem|**Ativado**|Modelo|Sim|
|Chat de reunião|**Somente em reunião**|Modelo|Sim|
|Pessoas discagem pode ignorar o lobby|**Desativado**|Rótulo|Sim|
|Impedir a cópia do conteúdo do chat na área de transferência|**Ativado**|Rótulo|Sim|
|Gravar automaticamente|(Desabilitado devido à marca d'água e criptografia)|Não disponível|Não disponível|
|Quem pode ignorar o lobby|**Apenas organizadores e co-organizadores**|Rótulo|Sim|
|Quem pode apresentar|**Apenas organizadores e co-organizadores**|Rótulo|Sim|
|Quem pode gravar|(Desabilitado devido à marca d'água e criptografia)|Não disponível|Não disponível|

As configurações listadas como impostas são impostas pelo rótulo de confidencialidade ou pelo modelo de reunião. As configurações que não são impostas podem ser alteradas pelo organizador da reunião.

#### <a name="highly-sensitive-presentations"></a>Apresentações altamente sensíveis

Para apresentações altamente sensíveis - onde não esperamos interação com os participantes da reunião - desligaremos os microfones e as câmeras dos participantes e desligaremos o chat da reunião.

Se você quiser permitir que os participantes façam perguntas ao apresentador, os organizadores da reunião podem ativar o recurso Q&A. (Certifique-se de que ele está habilitado nas políticas de reunião de administrador do Teams.)

A tabela a seguir descreve quais ações restringiremos para apresentações altamente confidenciais e onde essas configurações estão configuradas.

|Recurso|Configuração|Localização|Aplicada|
|:------|:------|:-------|:-------|
|Permitir câmera para participantes|**Desativado**|Modelo|Sim|
|Permitir microfone para participantes|**Desativado**|Modelo|Sim|
|Aplicar uma marca d'água ao feed de vídeo de todos|**Ativado**|Rótulo|Sim|
|Aplicar uma marca d'água ao conteúdo compartilhado|**Ativado**|Rótulo|Sim|
|Criptografia de ponta a ponta|**Ativado**|Rótulo|Sim|
|Gerenciar o que os participantes veem|**Ativado**|Modelo|Sim|
|Chat de reunião|**Desativado**|Modelo|Sim|
|Pessoas discagem pode ignorar o lobby|**Desativado**|Rótulo|Sim|
|Impedir a cópia do conteúdo do chat na área de transferência|**Ativado**|Rótulo|Sim|
|Gravar automaticamente|(Desabilitado devido à marca d'água e criptografia)|Não disponível|Não disponível|
|Quem pode ignorar o lobby|**Apenas organizadores e co-organizadores**|Rótulo|Sim|
|Quem pode apresentar|**Apenas organizadores e co-organizadores**|Rótulo|Sim|
|Quem pode gravar|(Desabilitado devido à marca d'água e criptografia)|Não disponível|Não disponível|

As configurações listadas como impostas são impostas pelo rótulo de confidencialidade ou pelo modelo de reunião. As configurações que não são impostas podem ser alteradas pelo organizador da reunião.

## <a name="options-for-recording-meetings"></a>Opções para reuniões de gravação

Para o nível *altamente sensível* de proteção, usamos marca d'água e criptografia de ponta a ponta para reuniões e apresentações. No entanto, o uso desses recursos impede a gravação da reunião. Se você tiver a necessidade de registrar reuniões altamente confidenciais, recomendamos não configurar marcas d'água e criptografia de ponta a ponta como parte do rótulo de confidencialidade. Eles ainda podem ser usados pelos organizadores da reunião para reuniões que não precisam gravar.

## <a name="presentation-options-for-highly-sensitive-meetings"></a>Opções de apresentação para reuniões altamente sensíveis

Para reuniões *altamente sensíveis* , estamos impondo configurações específicas para quem pode apresentar, bem como como o conteúdo é compartilhado.

Ao **ativar Gerenciar o que os participantes podem ver**, garantimos que os organizadores da reunião possam examinar o conteúdo compartilhado antes que ele seja colocado na tela para os participantes. Neste exemplo, estamos usando um modelo para ativar isso por padrão, mas você também pode aplicá-lo no modelo, se necessário.

Ao definir **Quem pode apresentar** **somente organizadores e co-organizadores** no rótulo de confidencialidade, garantimos que as únicas pessoas que podem apresentar são aquelas que o organizador da reunião pretende.

## <a name="lobby-options-for-sensitive-meetings"></a>Opções de lobby para reuniões confidenciais

Usaremos o rótulo de confidencialidade para impedir que qualquer um que não seja os organizadores da reunião ignore o lobby. Isso permite que os organizadores vetem cada participante e verifiquem se eles devem ser admitidos.

## <a name="participation-options-for-highly-sensitive-meetings"></a>Opções de participação para reuniões altamente sensíveis

Embora o chat possa ser controlado com o rótulo de confidencialidade, usaremos modelos nesse caso para que os modelos de reunião e apresentação possam compartilhar o mesmo rótulo. Restringiremos o chat à reunião apenas para reuniões e o desativaremos completamente para apresentações. (Os organizadores podem usar o recurso Q&A em apresentações para permitir comentários ou perguntas do público.)

Para reuniões e apresentações, também impediremos a cópia do conteúdo do chat na área de transferência.

Enquanto deixaremos o microfone e a câmera do participante habilitados para reuniões, vamos desativá-los para apresentações.

## <a name="sensitivity-labels"></a>Rótulos de confidencialidade

Para o nível sensível de proteção, usaremos um rótulo de confidencialidade que você pode usar diretamente em uma reunião ou como parte de um modelo de reunião. Dependendo da configuração escolhida, esse rótulo também pode ser usado para classificar equipes e arquivos individuais.

Se você já tiver rótulos de confidencialidade implantados em sua organização, considere como esse rótulo se encaixa com sua estratégia geral de rótulo. Você pode alterar o nome ou as configurações, se necessário, para atender às necessidades da sua organização. Se você já tiver um rótulo que usa para obter informações confidenciais, poderá editar o rótulo e adicionar reuniões do Teams a ele.

> [!IMPORTANT]
> Se um rótulo de confidencialidade que restringe a cópia do chat for especificado como o rótulo de canal padrão em um rótulo de contêiner, as equipes com esse rótulo de contêiner restringirão a cópia do chat para todos os canais da equipe, dentro e fora das reuniões de canal.

Para criar um rótulo de confidencialidade
1. Abra o [portal de conformidade do Microsoft Purview](https://compliance.microsoft.com).
1. Em **Soluções**, clique em **Proteção de informações**.
1. Clique **em Criar um rótulo**.
1. Dê um nome ao rótulo. Sugerimos **altamente sensível**, mas você pode escolher um nome diferente se esse já estiver em uso.
1. Adicione um nome de exibição e uma descrição e clique em **Avançar**.
1. Na página **Definir o escopo para este rótulo** , selecione **Itens** e **Incluir reuniões**. (Observe que você pode selecionar outras opções se quiser usar esse rótulo para outras finalidades.)
1. Selecione **Avançar**.
1. Continue selecionando as opções que você deseja usar com este rótulo e, em seguida, na página **Configurações para reuniões e chats do Teams** , escolha os seguintes valores:
    1. Selecione **Controle que pode ignorar o lobby** e selecione **Somente organizadores e co-organizadores** na lista suspensa.
    1. Verifique se **permitir que os usuários discados ignorem o lobby** está desmarcado
    1. Selecione **Controle que pode apresentar** e selecione **Somente organizadores e co-organizadores** na lista suspensa.
    1. Selecione **Controlar criptografia de ponta a ponta para vídeo e áudio de reunião e** , em seguida, defina **Aplicar criptografia de ponta a ponta** como **Ativado**.
    1. Selecione **Controlar marcas d'água** e, em seguida, defina **Aplicar marca d'água ao conteúdo compartilhado** e **Aplicar marca d'água ao feed de vídeo de todos para Ativar**.
    1. Selecione **Impedir copiar conteúdo de chat para a área de transferência**.
    1. Configure quaisquer outras configurações necessárias para sua organização.
    <!--:::image type="content" source="media/teams-meeting-sensitivity-label-highly-sensitive-small.png" alt-text="Screenshot of sensitivity label meeting settings." lightbox="media/teams-meeting-sensitivity-label-highly-sensitive-large.png":::-->
1. Selecione **Avançar**.
1. Conclua o assistente com as configurações adicionais que você deseja usar e selecione **Criar rótulo** e selecione **Concluído**.

Depois de criar o rótulo, você precisará publicá-lo para os usuários que o usarão. Para proteção altamente confidencial, disponibilizaremos o rótulo para todos os usuários. Você publica o rótulo no portal de conformidade do Microsoft Purview, na guia **Políticas** de rótulo da página **Proteção de informações**. Se você tiver uma política existente que se aplique a todos os usuários, adicione esse rótulo a essa política. Se você precisar criar uma nova política, consulte [Publicar rótulos de confidencialidade criando uma política de rótulo](/compliance/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy).

Para obter informações adicionais sobre como usar rótulos de confidencialidade com reuniões, consulte [Usar rótulos de confidencialidade para proteger itens de calendário, reuniões do Teams e chat](/microsoft-365/compliance/sensitivity-labels-meetings).

## <a name="meeting-templates"></a>Modelos de reunião

No nível de proteção *altamente sensível* , estamos configurando as seguintes configurações usando um modelo de reunião:

- **Permitir câmera para participantes** -  **Ativado**, mas não imposto para reuniões e imposto **para** apresentações.
- **Permitir microfone para participantes** -  **Ativado**, mas não imposto para reuniões e imposto **para** apresentações.
- **Gerenciar o que os participantes podem ver** – Imposto **para** reuniões e apresentações.
- **Chat de reunião** – imposto à **reunião somente** para reuniões e imposto a **Off** para apresentações.

Como essas configurações diferem entre reuniões e apresentações, criaremos um modelo para cada um que compartilhe o mesmo rótulo de confidencialidade.

#### <a name="highly-sensitive-meetings-template"></a>Modelo de reuniões altamente confidenciais

Para criar um modelo de reunião para reuniões altamente sensíveis

1. No centro de administração do Teams, expanda **Reuniões** e selecione **Modelos de reunião**.
1. Selecione **Adicionar**
1. Digite um nome e uma descrição para o modelo.
1. Na seção **Aplicar rótulo de confidencialidade** , escolha o rótulo que você criou acima.
1. Selecione **Aplicar rótulo de confidencialidade** e selecione **Bloquear**.
1. Defina **o chat da reunião** **apenas como reunião** e selecione a configuração e selecione **Bloquear**.
1. Defina **Gerenciar o que os participantes veem** **como Ativado** e selecione a configuração e selecione **Bloquear**.
1. Altere as configurações adicionais, se desejar.
1. Para impedir que o organizador da reunião altere uma configuração, selecione a configuração e selecione **bloquear**.
1. Para impedir que o organizador da reunião veja uma configuração, selecione a configuração e selecione **Ocultar**.
1. Selecione **Salvar**.

#### <a name="highly-sensitive-presentations-template"></a>Modelo de apresentações altamente sensível

Para criar um modelo de reunião para apresentações altamente sensíveis

1. No centro de administração do Teams, expanda **Reuniões** e selecione **Modelos de reunião**.
1. Selecione **Adicionar**
1. Digite um nome e uma descrição para o modelo.
1. Na seção **Aplicar rótulo de confidencialidade** , escolha o rótulo que você criou acima.
1. Selecione **Aplicar rótulo de confidencialidade** e selecione **Bloquear**.
1. Defina **Permitir microfone para os participantes** como **Ativado** e selecione a configuração e selecione **Bloquear**.
1. Defina **Permitir câmera para os participantes** como **Ativado** e selecione a configuração e selecione **Bloquear**.
1. Defina **o chat da reunião** como **Desativado** e selecione a configuração e selecione **Bloquear**.
1. Defina **Gerenciar o que os participantes veem** **como Ativado** e selecione a configuração e selecione **Bloquear**.
1. Altere as configurações adicionais, se desejar.
1. Para impedir que o organizador da reunião altere uma configuração, selecione a configuração e selecione **bloquear**.
1. Para impedir que o organizador da reunião veja uma configuração, selecione a configuração e selecione **Ocultar**.
1. Selecione **Salvar**.

## <a name="related-topics"></a>Tópicos relacionados

[Configurar reuniões do Teams com três camadas de proteção](configure-meetings-three-tiers-protection.md)

[Visão geral dos modelos de reunião personalizados no Microsoft Teams](custom-meeting-templates-overview.md)

[Use modelos de reunião do Teams, rótulos de confidencialidade e políticas de administrador juntos para reuniões confidenciais](meeting-templates-sensitivity-labels-policies.md)

[Usar rótulos de confidencialidade para proteger itens de calendário, reuniões do Teams e chat](/microsoft-365/compliance/sensitivity-labels-meetings)
