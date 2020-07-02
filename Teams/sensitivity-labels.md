---
title: Rótulos de sensibilidade do Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: abgupta
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: Saiba como definir e usar rótulos de sensibilidade no Microsoft Teams.
ms.openlocfilehash: 2940fd5537f02a6d5b3125f4c0037b9705571ffa
ms.sourcegitcommit: a94a267c421a78587b0dbbea5fa167aad2882e9b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2020
ms.locfileid: "45012307"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a>Rótulos de sensibilidade do Microsoft Teams

Os [Rótulos de sensibilidade](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) permitem que os administradores de equipe regulam o acesso a conteúdo organizacional confidencial criado durante a colaboração dentro do teams. Você pode definir rótulos de sensibilidade e suas políticas associadas no [centro de conformidade de & de segurança](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center). Esses rótulos e políticas são automaticamente aplicados ao Teams em sua organização.  

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a>Qual é a diferença entre rótulos de sensibilidade e rótulos de classificação de equipes?

Rótulos de sensibilidade são diferentes dos rótulos de classificação que exigem que você os crie usando o PowerShell. Os rótulos de classificação são cadeias de caracteres de texto que podem ser associadas a um grupo, mas não têm políticas reais associadas a eles. Você usa rótulos de classificação como metadados para impor políticas manualmente por meio de ferramentas e scripts internos.

Por outro lado, as etiquetas de sensibilidade e suas políticas são automaticamente impostas de ponta a ponta por meio de uma combinação da plataforma de grupos, do centro de conformidade & do centro de conformidade e dos serviços do teams. Os rótulos de sensibilidade fornecem suporte avançado à infraestrutura para proteger os dados confidenciais da sua organização.  

Para migrar seus grupos existentes de rótulos de classificação para usar rótulos de sensibilidade, use as instruções em [Rótulos de classificação e sensibilidade do Azure Active Directory para grupos do Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/migrate-aad-classification-sensitivity-labels).
## <a name="create-manage-and-publish-sensitivity-labels-for-teams"></a>Criar, gerenciar e publicar rótulos de sensibilidade para equipes

Para saber como habilitar, criar e publicar rótulos de sensibilidade para equipes, consulte [Rótulos de classificação e sensibilidade do Azure Active Directory para grupos do Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).

>[!IMPORTANT]
>Criar, atualizar e excluir rótulos de sensibilidade exigem sequenciamento cuidadoso com rótulos de publicação para usuários. Qualquer desvio na sequência pode resultar em erros persistentes de criação de equipe para todos os usuários. Portanto, é essencial fazer o seguinte quando você <a href="#createpublishlabels">cria e publica rótulos</a>, <a href="#modifydeletelabels">modifica e exclui rótulos publicados</a>e <a href="#manageerrors">gerencia erros de criação de equipe</a>.

**Criar e publicar rótulos** <a name="createpublishlabels"> </a>

Quando um rótulo é criado e publicado no centro de conformidade do & de segurança, pode levar até 10 minutos para o rótulo ficar visível na interface de criação do Microsoft Teams. Use as etapas a seguir para publicar o rótulo para todos os usuários no locatário:
1. Crie o rótulo e publique-o para algumas contas de usuário selecionadas no locatário.
2. Quando o rótulo for publicado, aguarde 10 minutos.
3. Após 10 minutos, tente criar uma equipe com o rótulo usando uma das contas de usuário que têm acesso ao rótulo.
4. Se a equipe criou com êxito a etapa 3, siga em frente e publique o rótulo dos usuários remanescentes no locatário.

**Modificar e excluir rótulos publicados** <a name="modifydeletelabels"> </a>

Excluir ou modificar o rótulo enquanto ele está associado a políticas de sensibilidade pode resultar em falhas de criação de equipe em todo o locatário. Portanto, antes de excluir ou modificar um rótulo, primeiro você deve desassociar o rótulo de suas políticas associadas. Use as etapas a seguir  
para excluir ou modificar um rótulo:
1. Remova o rótulo de todas as políticas que usam o rótulo. Ou, se preferir, você também pode excluir as próprias políticas.
2. Quando o rótulo é removido das políticas ou as próprias diretivas são excluídas, aguarde 10 minutos antes de prosseguir.
3. Após 10 minutos, inicie a interface de criação de equipe e certifique-se de que o rótulo não fique mais visível para qualquer usuário no locatário.
4. Agora você pode excluir ou modificar o rótulo com segurança.

**Gerenciar erros** <a name="manageerrors"> </a> de criação de equipe

Se a criação de equipe começar a falhar em qualquer ponto durante a visualização pública, você terá duas opções:
 - Certifique-se de que os rótulos de sensibilidade não sejam obrigatórios para qualquer usuário durante a criação da equipe.
 - Desative os rótulos de sensibilidade usando os scripts em [habilitar esta visualização](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#enable-this-preview).

Observe que a configuração EnableMIPLabels deve ser definida como false da seguinte maneira:

```console
$setting["EnableMIPLabels"] = "False"
```

## <a name="using-sensitivity-labels-with-teams"></a>Usar rótulos de sensibilidade com o Teams

Aqui estão alguns exemplos de cenários de como você pode usar rótulos de sensibilidade com o Teams em sua organização.

### <a name="privacy-setting-of-teams"></a>Configuração de privacidade do teams

Você pode criar um rótulo de sensibilidade que, quando aplicado durante a criação da equipe, permite que os usuários criem equipes com uma configuração específica de privacidade (pública ou particular).

Por exemplo, você pode criar um rótulo chamado "confidencial" no centro de conformidade do & de segurança e configurar o Microsoft Teams para que qualquer equipe criada com esse rótulo deve ser uma equipe privada. Quando um usuário cria uma nova equipe e seleciona o rótulo **confidencial** , a única opção de privacidade que está disponível para o usuário é **particular**. Outras opções de privacidade, como público e toda a organização, são desabilitadas para o usuário.

![Captura de tela de rótulo confidencial de confidencialidade](media/sensitivity-labels-confidential-example.png)

Da mesma forma, se o usuário selecionar **geral** quando criar uma nova equipe, ele só poderá criar equipes públicas ou de toda a organização.

![Captura de tela do rótulo de sensibilidade geral](media/sensitivity-labels-general-example.png)

Quando a equipe é criada, o rótulo de sensibilidade fica visível no canto superior direito dos canais da equipe.

![Captura de tela do rótulo de sensibilidade no canal de equipe](media/sensitivity-labels-channel.png)

Um proprietário de equipe pode alterar o rótulo de sensibilidade e a configuração de privacidade da equipe a qualquer momento, acessando a equipe e, em seguida, clicando em **Editar equipe**.

![Captura de tela do rótulo de sensibilidade no canal de equipe](media/sensitivity-labels-edit-team.png)

### <a name="guest-access-to-teams"></a>Acesso de convidado a equipes

Você pode especificar se uma equipe criada com um rótulo específico permite acesso de convidado. As equipes criadas com um rótulo que não permite acesso de convidado só estão disponíveis para os usuários da sua organização. Pessoas de fora da sua organização não podem ser adicionadas à equipe.

## <a name="known-issues"></a>Problemas conhecidos

**Rótulos padrão filho não exibidos durante a criação da equipe**

Atualmente, um rótulo filho definido como o rótulo padrão para equipes não será exibido na parte superior da lista na lista de rótulos de sensibilidade no modelo de criação de equipe. Os criadores de equipe ainda podem usar o menu suspenso para aplicar o rótulo filho como solução alternativa.

**Suporte para rótulos de sensibilidade no centro de administração do Microsoft Teams**

No momento, não há suporte para rótulos de sensibilidade no centro de administração do Microsoft Teams. Se você usar rótulos de sensibilidade, não poderá definir rótulos de sensibilidade ao criar ou editar uma equipe. Os rótulos de sensibilidade também não ficam visíveis nas propriedades da equipe e não ficarão visíveis na coluna **classificação** no centro de administração do Microsoft Teams.

**Suporte para rótulos de sensibilidade em APIs de gráficos do Teams, cmdlets e modelos do PowerShell**

Atualmente, os usuários não poderão aplicar rótulos de sensibilidade em equipes criadas diretamente por meio de APIs de gráfico, cmdlets e modelos do PowerShell.

**Suporte para rótulos de sensibilidade em SKUs EDU do teams**

No momento, os rótulos de sensibilidade não são aceitos para clientes que usam SKUs de educação do teams.

**Edição de rótulos de sensibilidade diretamente em um conjunto de sites do SharePoint para canais privados**

Os canais privados criados em uma equipe herdam o rótulo de sensibilidade que foi aplicado a uma equipe. Além disso, o mesmo rótulo é aplicado automaticamente no conjunto de sites do SharePoint para o canal privado.

Se um usuário atualizar diretamente o rótulo de sensibilidade em um conjunto de sites do SharePoint para um canal privado, esse rótulo não será atualizado no cliente do teams. Nesse cenário, os usuários continuarão a ver o rótulo de sensibilidade aplicado a uma equipe no cabeçalho do canal privado.

**Tempo de propagação de alterações aplicadas a rótulos de sensibilidade fora do aplicativo Teams**

As alterações feitas em rótulos de sensibilidade fora do aplicativo Teams podem levar até 24 horas para refletir no aplicativo Teams. Isso se aplica a qualquer alteração feita para habilitar ou desabilitar rótulos de um locatário, alterações em nomes de rótulo, configurações e políticas.

Além disso, qualquer alteração em um rótulo feito diretamente em um grupo ou conjunto de sites do SharePoint que faz backup da equipe pode levar até 24 horas para se propagar para o aplicativo Teams.
