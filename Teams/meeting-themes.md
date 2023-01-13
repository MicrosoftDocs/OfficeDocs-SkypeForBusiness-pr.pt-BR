---
title: Temas de reunião para reuniões do Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.localizationpriority: medium
search.appverid: MET150
description: Usando ativos corporativos aprovados, como imagens e logotipos, para criar alguns temas de reunião personalizados para reuniões do Teams em sua organização.
ms.openlocfilehash: 768c589507cac3f100d2760fe6497872a7f8ee00
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800230"
---
# <a name="meeting-themes-for-teams-meetings"></a>Temas de reunião para reuniões do Teams

[!INCLUDE[Teams Premium](includes/teams-premium-ecm.md)]

A personalização em reuniões do Teams permite que as organizações estendam suas identidades visuais pela experiência da reunião. As imagens e as cores de uma organização ajudam a promover a construção da cultura corporativa interna e aumentar a conscientização geral da marca com os convidados. Com a ajuda das equipes de gerenciamento de marca e comunicações corporativas de uma organização, os administradores de locatários podem facilmente configurar e criar temas de reunião para várias unidades de negócios e departamentos dentro de um único locatário.
Por padrão, os usuários licenciados premium do Teams que receberam uma política de personalização de reunião podem criar reuniões habilitadas para temas de reunião. Essas reuniões apresentam temas por padrão e qualquer pessoa que ingressar nas reuniões pode ver os temas (incluindo usuários internos sem licença, convidados e usuários anônimos).

> [!NOTE]
> Os participantes que ingressarem no Teams por meio da experiência da Web não poderão ver temas de reunião.

## <a name="prerequisites"></a>Pré-requisitos

Antes de configurar temas de reunião em Reuniões do Teams, verifique se você tem os seguintes itens:

- Acesso ao SKU Teams Premium
- Você é um administrador com acesso ao centro de administração do Teams ou recebeu uma política de personalização
- Seu [logotipo,](#adding-a-custom-logo-image) [imagem](#adding-a-custom-image) e [cor](#adding-a-custom-color) personalizados atendem às especificações necessárias

## <a name="setting-up-meeting-branding"></a>Configurando a marca de reunião

Os administradores de locatários podem configurar e gerenciar temas de reunião para reuniões do Teams no centro de administração do Teams.

### <a name="creating-a-customization-policy"></a>Criando uma política de personalização

Para criar temas de reunião, os administradores primeiro precisarão criar uma nova política de personalização de reunião ou modificar sua política existente.
Para habilitar a política de plano de fundo personalizada, os administradores executarão as seguintes etapas:

1. Abrir o centro de administração do Teams
2. Selecione **Reuniões** no painel de navegação
3. Em **Reuniões**, selecione **Políticas de Personalização**
4. Selecione uma política existente ou crie uma nova
5. Na política escolhida, navegue até a seção **Visuals de Reunião Personalizada**
6. Alternar a configuração **Atualmente Ativa** de desativada para **ativar** para habilitar a configuração
7. Selecione **Salvar** para habilitar temas de reunião

> [!NOTE]
> Embora você possa acessar visuais de reunião personalizados na página Políticas de Reunião, recomendamos acessá-lo por meio de Políticas de Personalização para evitar a navegação por meio de políticas padrão da organização global.

Dentro da política de personalização da reunião, os administradores podem começar a definir sua identidade visual criando um tema de reunião.

Os temas de reunião abrigam os seguintes ativos para seu tema:

- Logotipo – imagem do logotipo da sua organização.
- Imagem personalizada – uma imagem de marca de sua organização (imagens personalizadas não são [iguais a planos de fundo de reunião personalizados](custom-meeting-backgrounds.md)).
- Cor personalizada – é recomendável usar a cor primária ou secundária da sua marca – o que melhor complementa sua imagem e logotipo da marca.

Para criar um novo tema, selecione **Adicionar tema de reunião**.

### <a name="adding-a-custom-logo-image"></a>Adicionando uma imagem de logotipo personalizada

O Teams Meetings dá suporte a logotipos quadrados que aparecem em superfícies-chave durante a reunião, incluindo a tela do lobby. As imagens de logotipo devem atender às taxas de contraste de acessibilidade da Microsoft (4:5:1).

Os uploads devem seguir os parâmetros a seguir. Um administrador só pode carregar:

- Formatos de imagem PNG e JPEG para seu logotipo.
- Uma imagem de logotipo com um tamanho máximo de 5 MB.
- Imagens de logotipo com uma dimensão mínima de 576 px X 576 px.
- Apenas uma imagem por tema de seu dispositivo.

### <a name="adding-a-custom-image"></a>Adicionar uma imagem personalizada

As reuniões do Teams dão suporte às imagens de uma organização que esfolam a tela de reuniões e fornecem um cenário colorido para suas reuniões.

> [!NOTE]
> Essas imagens não são iguais aos [planos de fundo de reunião personalizados](custom-meeting-backgrounds.md)

As imagens personalizadas devem atender às taxas de contraste de acessibilidade da Microsoft (4:5:1) e os uploads devem seguir estes parâmetros:

- Administração só pode carregar formatos de imagem PNG e JPEG para imagem de marca
- Administração só pode carregar imagem da marca com tamanho máximo de 5 MB
- Administração pode carregar a imagem da marca com as seguintes dimensões:
  - Dimensões mínimas: 360 px X 360 px
  - Dimensões máximas: 2048 px X 2048 px
- Administração pode carregar um mínimo de 0 e um máximo de uma imagem por tema de seu dispositivo

### <a name="adding-a-custom-color"></a>Adicionar uma cor personalizada

As reuniões do Teams dão suporte à cor primária ou secundária de uma organização na experiência de reunião. Você pode inserir o valor de código hex da cor da sua organização, que aparecerá nas principais superfícies da experiência de reunião.

> [!NOTE]
> Para dar suporte aos padrões de acessibilidade da Microsoft, a cor final gerada pode não corresponder à cor da marca.

### <a name="previewing-a-meeting-theme"></a>Visualizando um tema de reunião

Depois de adicionar seus ativos de reunião, você pode visualizar como seu tema será antes de salvar.  Selecionar **Visualização** abrirá a caixa de diálogo de visualização e mostrará o tema recém-definido para área de trabalho e móvel.

### <a name="save-meeting-theme"></a>Salvar tema da reunião

Ao selecionar **Salvar**, o tema da reunião é salvo automaticamente e aplicado às suas reuniões. Selecionar **Salvar e solicitar posteriormente** salvará o tema da reunião, mas não o aplicará a nenhuma de suas reuniões. Para aplicar esse tema, selecione **Salvar** no criador do tema da reunião ou use o alternância **atualmente ativo** na tabela de tema da reunião na página de política de personalização.



### <a name="assigning-a-meeting-customization-policy-to-users"></a>Atribuindo uma política de personalização de reunião aos usuários

As políticas de personalização de reunião podem ser atribuídas a um, muitos ou a um grupo de usuários pré-definido em seu Locatário. Verifique se esses usuários têm uma licença premium do Teams para usar esses recursos.

- Por padrão, todos os usuários licenciados receberão a política Padrão Global atribuída a eles.
- As políticas de personalização personalizadas substituirão o padrão global
- Um usuário licenciado só pode receber uma política de personalização

### <a name="use-cases-for-multiple-departments-or-business-units-in-one-tenant"></a>Usar casos para vários departamentos ou unidades de negócios em um locatário

Algumas organizações têm várias unidades de negócios sob identidades de marca diferentes dentro do mesmo locatário. Nesses casos, os administradores podem criar políticas de personalização de reunião dedicadas a cada marca. Eles também podem atribuir um grupo de usuários de unidade de negócios ou departamento a uma política específica.

#### <a name="a-use-case"></a>Um caso de uso

A Contoso Ltd. tem um único locatário no Microsoft Teams, contendo os perfis de usuário de todos os seus funcionários em diferentes organizações empresariais. A empresa está procurando adotar reuniões personalizadas de marca no Teams para aumentar sua presença de marca com seus clientes e incentivar uma cultura corporativa interna.

A Contoso tem duas BUs (unidades de negócios) em sua organização: Contoso Technical Services e Contoso Education. Ambas as BUs têm suas próprias imagens de marca distintas e querem exibir sua identidade visual durante suas reuniões internas e externas.

Para dar suporte a esse caso de uso, os administradores de locatários podem criar duas políticas de personalização distintas:

- Política A – Serviços Técnicos da Contoso – abriga o logotipo, a imagem e a cor da marca do Serviço Técnico da Contoso
- Política B – Contoso Education – abriga o logotipo, a imagem e a cor da marca da Contoso Education

Eles podem continuar atribuindo os funcionários licenciados nos Serviços Técnicos da Contoso à Política A e funcionários licenciados da Contoso Education à Política B.

## <a name="where-are-meeting-themes-visible"></a>Onde estão visíveis os temas de reunião

Clientes com suporte:

- Cliente de desktop
- Android (somente versões 11+)
- iOS

|         | Iniciador de Ingresso | Pré-ingressamento da reunião | Lobby da Reunião | Estágio de Reunião |
| :---:          |     :---:      |         :---:  |         :---:  |         :---:  |
| **Logotipo**   | Não | Sim| Sim| Sim|
| **Imagem**     | Não | Sim| Sim| Sim|
| **Cor**     | Sim | Sim| Sim| Sim|

Logotipos e imagens estarão disponíveis para o Join Launcher em atualizações futuras.
> [!NOTE]
> A nova experiência webinar usará esses recursos de tema em reuniões. A página de registro de webinar ainda será usada para configurar a identidade visual do webinar para registro de reunião e emails. Os organizadores da reunião podem desativar os temas da reunião para um webinar optando por opções de reunião. Saiba mais sobre [a nova experiência webinar](set-up-webinars.md)

### <a name="who-can-view-a-meeting-theme"></a>Quem pode exibir um tema de reunião

Embora apenas usuários licenciados que recebem uma política de personalização de reunião possam criar reuniões habilitadas para temas de reunião, qualquer pessoa pode exibir os temas que são aplicados a uma reunião. Esses usuários incluem:

- In-tenant, Teams Premium usuários licenciados
- Usuários in-tenant e não licenciados
- Convidado de usuários locatários
- Usuários Externos
- Usuários anônimos

### <a name="how-to-turn-off-meeting-themes-for-a-meeting"></a>Como desativar temas de reunião para uma reunião

Os administradores de locatários podem permitir que os organizadores da reunião desabilitem temas de reunião para uma instância de reunião específica. Desabilitar temas de reunião retornará a reunião ao tema padrão do Teams.

Para dar aos organizadores da reunião a capacidade de desabilitar temas de reunião:

1. Navegue até a **política de personalização da reunião**.
1. Alterne a configuração **"Tema da Reunião" que permite que os organizadores desativem o tema da reunião para reuniões específicas**.

Os organizadores da reunião podem desativar os temas da reunião por:

1. Navegando até o menu **opções de reunião** para uma instância de reunião.
1. Alternar a opção de reunião **Permitir que os organizadores desativem o tema da reunião**.

> [!NOTE]
>
> - Para reuniões ou séries recorrentes, a opção de reunião se aplicará a cada instância da reunião.
> - Os temas de reunião não serão desabilitados para reuniões em andamento. Para aplicar alterações, você deve encerrar a chamada e reiniciar a reunião.

## <a name="best-practices-for-meeting-themes"></a>Práticas recomendadas para temas de reunião

- Use apenas os ativos de imagem oficiais da sua organização. Não use o conteúdo de imagem que você não possui.
- Trabalhe com sua equipe de marca e marketing para garantir que seus ativos de imagem e cores sigam as diretrizes de marca da sua organização.
- Verifique se você está usando imagens de logotipo de alta qualidade, que são visíveis em dispositivos de tela pequena e grande.
- As cores geradas no Aplicativo teams podem ser diferentes das cores da sua marca. Esse processo foi criado para garantir que os Padrões de Acessibilidade da Microsoft sejam atendidos.
- Usuários com configurações de dispositivo de alto contraste não verão temas de reunião.

### <a name="accessibility"></a>Acessibilidade

Aqui estão alguns pontos para garantir que os requisitos de acessibilidade sejam atendidos:

- Siga padrões e estrutura de interface do usuário existentes – a estrutura e o texto atuais na tela não estão sendo modificados com esse recurso.
- Taxa de contraste de imagem – os ativos de imagem são necessários para atender à taxa de contraste de cores 4:5:1.  
- Suporte à Geração de Cores Acessível – calculamos a saída de cor acessível que é a mais próxima da entrada de cor da marca, mantendo os padrões de acessibilidade da Microsoft  
- Suporte a Alto Contraste – Para usuários com configurações de alto contraste habilitadas, a identidade visual não se aplica. Eles continuarão a ver a experiência de reunião padrão do Teams.
- Controles de Administração de TI – os administradores de TI podem impedir que usuários com preocupações de acessibilidade vejam a identidade visual: 
  - Controle de política – garantindo que eles não sejam adicionados a uma política de personalização. Esse controle impedirá que eles criem reuniões habilitadas para identidade visual.
  - Opções de reunião – os organizadores da reunião podem desativar a identidade visual para uma reunião se um usuário com preocupações de acessibilidade participar da reunião.
