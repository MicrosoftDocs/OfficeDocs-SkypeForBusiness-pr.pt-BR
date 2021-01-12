---
title: Rótulos de sensibilidade para o Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
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
ms.openlocfilehash: d021954a32cc2d93fb7b17726720396e66b4fd39
ms.sourcegitcommit: b68a7b5100fc2b47ae81f465d48d1ac2348c1744
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/11/2021
ms.locfileid: "49795766"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a>Rótulos de sensibilidade para o Microsoft Teams

[Os rótulos de sensibilidade](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) permitem que os administradores do Teams regulam o acesso a conteúdos organizacionais confidenciais criados durante a colaboração nas equipes. Você pode definir rótulos de sensibilidade e suas políticas associadas no Centro [de Conformidade.](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center) Esses rótulos e políticas são aplicados automaticamente às equipes em sua organização.  

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a>Qual é a diferença entre rótulos de sensibilidade e rótulos de classificação do Teams?

Os rótulos de sensibilidade são diferentes dos rótulos de classificação. Rótulos de classificação são cadeias de caracteres de texto que podem ser associadas a um grupo do Microsoft 365, mas não têm políticas reais associadas a eles. Você usa rótulos de classificação como metadados para impor manualmente políticas por meio de scripts e ferramentas internas.

Por outro lado, os rótulos de sensibilidade e suas políticas são automaticamente impostos de ponta a ponta por meio de uma combinação da plataforma grupos, do Centro de Conformidade e & segurança e dos serviços do Teams. Os rótulos de sensibilidade oferecem suporte poderoso à infraestrutura para proteger os dados confidenciais da sua organização.  

Para migrar seus grupos existentes do uso de rótulos de classificação para usar rótulos de sensibilidade, use as instruções nos rótulos de classificação e sensibilidade do Azure Active Directory para grupos [do Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/migrate-aad-classification-sensitivity-labels)

## <a name="create-manage-and-publish-sensitivity-labels-for-teams"></a>Criar, gerenciar e publicar rótulos de sensibilidade para o Teams

Para saber como habilitar, criar e publicar rótulos de sensibilidade para o Teams, consulte Usar rótulos de sensibilidade para proteger o conteúdo no Microsoft Teams, grupos [do Microsoft 365 e sites do SharePoint.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

>[!IMPORTANT]
>Criar, atualizar e excluir rótulos de sensibilidade exigem sequenciamento cuidadoso com rótulos de publicação para os usuários. Qualquer desvio na sequência pode resultar em erros persistentes de criação de equipe para todos os usuários. Portanto, é fundamental fazer o seguinte <a href="#createpublishlabels"></a>ao criar e publicar <a href="#manageerrors">rótulos,</a>modificar e excluir rótulos publicados <a href="#modifydeletelabels">e</a>gerenciar erros de criação de equipe.

**Criar e publicar rótulos** <a name="createpublishlabels"></a>

Quando um rótulo é criado e publicado no Centro de Conformidade, pode levar até 10 minutos para que o rótulo se torne visível na interface de criação de equipes. Use as etapas a seguir para publicar o rótulo de todos os usuários no locatário:
1. Crie o rótulo e publique-o para algumas contas de usuário selecionadas no locatário.
2. Quando o rótulo for publicado, aguarde 10 minutos.
3. Após 10 minutos, tente criar uma equipe com o rótulo usando uma das contas de usuário que têm acesso ao rótulo.
4. Se a equipe tiver criado com êxito na etapa 3, vá em frente e publique o rótulo para os usuários restantes no locatário.

**Modificar e excluir rótulos publicados** <a name="modifydeletelabels"></a>

Excluir ou modificar o rótulo enquanto ele estiver associado a políticas de sensibilidade pode resultar em falhas de criação de equipe em todo o locatário. Portanto, antes de excluir ou modificar um rótulo, primeiro você deve desassociar o rótulo de suas políticas associadas. Use as etapas a seguir  
para excluir ou modificar um rótulo:
1. Remova o rótulo de todas as políticas que usam o rótulo. Como alternativa, você também pode excluir as políticas por conta própria.
2. Quando o rótulo for removido das políticas ou as políticas em si são excluídas, aguarde 10 minutos antes de prosseguir.
3. Após 10 minutos, iniciar a interface de criação de equipe e garantir que o rótulo não seja mais visível para qualquer usuário no locatário.
4. Agora você pode excluir ou modificar o rótulo com segurança.

**Gerenciar erros de criação de equipe** <a name="manageerrors"></a>

Se a criação da equipe começar a falhar a qualquer momento durante a visualização pública, você terá duas opções:
 - Verifique se os rótulos de sensibilidade não são obrigatórios para qualquer usuário durante a criação da equipe.
 - Desativar rótulos de sensibilidade usando os scripts em [Habilitar esta visualização.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#enable-this-preview)

Observe que a configuração EnableMIPLabels deve ser definida como false da seguinte forma:

```console
$setting["EnableMIPLabels"] = "False"
```

## <a name="using-sensitivity-labels-with-teams"></a>Usando rótulos de sensibilidade com o Teams

Aqui estão alguns cenários de exemplo de como você pode usar rótulos de sensibilidade com o Teams em sua organização.

### <a name="privacy-setting-of-teams"></a>Configuração de privacidade das equipes

Você pode criar um rótulo de sensibilidade que, quando aplicado durante a criação da equipe, permite que os usuários criem equipes com uma configuração de privacidade específica (pública ou privada).

Por exemplo, você cria um rótulo chamado "Confidencial &" no Centro de Conformidade e Segurança e configura o Teams para que qualquer equipe criada com esse rótulo seja uma equipe privada. Quando um usuário cria uma nova  equipe e seleciona o rótulo Confidencial, a única opção de privacidade disponível para o usuário é **Particular**. Outras opções de privacidade, como Público e toda a organização, estão desabilitadas para o usuário.

![Captura de tela do rótulo confidencial de confidencialidade](media/sensitivity-labels-confidential-example.png)

Da mesma forma, se o usuário selecionar **Geral** ao criar uma nova equipe, ele só poderá criar equipes públicas ou em toda a organização.

![Captura de tela do rótulo de sensibilidade geral](media/sensitivity-labels-general-example.png)

Quando a equipe é criada, o rótulo de sensibilidade fica visível no canto superior direito dos canais da equipe.

![Captura de tela do rótulo de sensibilidade no canal de equipe](media/sensitivity-labels-channel.png)

Um proprietário da equipe pode alterar o rótulo de sensibilidade e a configuração de privacidade da equipe a qualquer momento, indo para a equipe e clicando em **Editar equipe.**

![Captura de tela do rótulo de sensibilidade nas propriedades da equipe](media/sensitivity-labels-edit-team.png)

### <a name="guest-access-to-teams"></a>Acesso de convidados às equipes

Você pode especificar se uma equipe criada com um rótulo específico permite o acesso de convidados. As equipes criadas com um rótulo que não permite o acesso de convidados estão disponíveis apenas para usuários em sua organização. Pessoas de fora da sua organização não podem ser adicionadas à equipe.

### <a name="sensitivity-labels-in-the-microsoft-teams-admin-center"></a>Rótulos de sensibilidade no centro de administração do Microsoft Teams

Você pode definir rótulos de sensibilidade ao criar ou editar uma equipe no centro de administração do Microsoft Teams. Os rótulos de sensibilidade também são  visíveis nas propriedades da equipe e na coluna Classificação, na página Gerenciar equipes do centro de administração do Microsoft Teams.

## <a name="known-issues"></a>Problemas conhecidos

**Suporte para rótulos de sensibilidade nas APIs do Teams Graph, cmdlets e modelos do PowerShell**

Atualmente, os usuários não poderão aplicar rótulos de sensibilidade em equipes criadas diretamente por meio de APIs do Graph, cmdlets do PowerShell e modelos.

**Suporte para rótulos de sensibilidade em SKUs EDU do Teams**

No momento, os rótulos de sensibilidade não têm suporte para clientes que usam SKUs do Teams Education.

**Editando rótulos de sensibilidade diretamente em um conjunto de sites do SharePoint para canais privados**

Os canais privados criados em uma equipe herdam o rótulo de sensibilidade que foi aplicado em uma equipe. Além disso, o mesmo rótulo é aplicado automaticamente no conjunto de sites do SharePoint para o canal privado.

Se um usuário atualizar diretamente o rótulo de sensibilidade em um conjunto de sites do SharePoint para um canal privado, esse rótulo não será atualizado no cliente do Teams. Nesse cenário, os usuários continuarão a ver o rótulo de sensibilidade aplicado em uma equipe no header de canal privado.

**Tempos de propagação para alterações aplicadas a rótulos de sensibilidade fora do aplicativo Teams**

As alterações feitas em rótulos de sensibilidade fora do aplicativo Teams podem levar até 24 horas para refletir no aplicativo Teams. Isso se aplica a quaisquer alterações feitas para habilitar ou desabilitar rótulos para um locatário, alterações em nomes de rótulos, configurações e políticas.

Além disso, qualquer alteração em um rótulo feita diretamente em um grupo ou conjunto de sites do SharePoint que dê apoio à equipe pode levar até 24 horas para se propagar para o aplicativo Teams.
