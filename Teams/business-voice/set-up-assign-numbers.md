---
title: Atribuir números de telefone do Business Voice aos seus usuários
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: Saiba como atribuir números Microsoft 365 Business Voice telefone a usuários em sua organização.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6d4b32b6a255ef806e86848d068dc988548988a75fb76c16d2dc4334b0d51d7d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54282844"
---
# <a name="step-5-assign-business-voice-phone-numbers-to-your-users"></a>Etapa 5: Atribuir números de telefone do Business Voice aos usuários

Antes que os usuários possam Teams para fazer ou receber chamadas telefônicas para ou de linhas telefônicas regulares, você precisa atribuir números de telefone a eles. Em Microsoft Teams clientes, o número de telefone que você atribui a um usuário é listado no bloco de discagem quando o usuário clica em **Chamadas**. Faça o seguinte para cada usuário que precisa de um número de telefone.

![Número de telefone do usuário exibido em Teams.](../media/teams-phone-number.png)

> [!NOTE]
> Se você não vir nenhum número de telefone, aguarde. Pode levar várias horas para que seus novos números de telefone se tornem disponíveis Teams.

O vídeo a seguir mostra como concluir essas etapas no Teams de administração.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4OFYO]

1. Abra o Microsoft Teams de administração e faça logoff com um usuário que seja um administrador global (geralmente essa é a conta que você usou para se inscrever no Microsoft 365).
1. No painel de navegação esquerdo, vá para Voz Telefone <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">   >  **números**</a>.
1. Na página **Telefone números,** selecione um número não atribuído na lista e clique em **Editar**.  
1. No painel **Editar,** em **Atribuído** a , procure o usuário por nome de exibição ou nome de usuário e clique em **Atribuir**.
1. Em **Local** de emergência , você pode selecionar [](set-up-emergency-locations.md) o local de emergência adicionado na etapa Configurar locais de emergência ou, se precisar criar um novo local para outro escritório ou um home office, clique em Adicionar **um local**.
1. Decida se deve enviar um email de boas-vindas com informações de número de telefone para o usuário. Se você quiser:
    - **Traga seus números de telefone existentes** para o Business Voice (chamada de portação de número de telefone), desmarque  **o usuário de email com informações de número de telefone**.
    - **Use os novos números de telefone selecionados** pelo Business Voice, *selecione* **Email user with phone number information**.
1. Clique em **Salvar**.
1. Repita as etapas acima para cada usuário ao qual você deseja atribuir um número de telefone.

> [!NOTE]
> Devido à latência entre Microsoft 365 ou Office 365 e Teams, pode levar até 24 horas para que os usuários sejam habilitados. Se o número de telefone não for atribuído corretamente após 24 horas, contate o suporte para produtos comerciais [- Ajuda do administrador](/microsoft-365/admin/contact-support-for-business-products). Estamos aqui para ajudar!

> [!div class="nextstepaction"]
> [Próxima etapa: Configurar um atendimento automático](set-up-auto-attendant.md?tabs=general-info#steps)
