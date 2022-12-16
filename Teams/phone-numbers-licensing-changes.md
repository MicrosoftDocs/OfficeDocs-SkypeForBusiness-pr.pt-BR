---
title: Números de telefone e alterações de licenciamento
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: ''
description: Saiba como as alterações de licenciamento podem afetar o gerenciamento de números de telefone.
ms.openlocfilehash: f75c5aeea577163e9f3ee6d1d4302836de0d1e7e
ms.sourcegitcommit: 321de0e5d8846caaaab944826f6ca06394e707ef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2022
ms.locfileid: "69414668"
---
# <a name="how-licensing-affects-phone-number-management"></a>Como o licenciamento afeta o gerenciamento de números de telefone

Como você remove e atribui licenças aos usuários pode afetar a capacidade de um usuário de fazer e receber chamadas PSTN (Rede Telefônica Comutada Pública) no Microsoft Teams. Este artigo descreve como você pode gerenciar alterações de licenciamento para garantir que a capacidade dos usuários de fazer e receber chamadas PSTN não seja afetada.

Para obter informações gerais sobre como gerenciar números de telefone, consulte [Gerenciar números de telefone para sua organização](manage-phone-numbers-landing-page.md). Para obter informações gerais sobre o licenciamento de complemento do Teams, consulte [Microsoft licenças de complemento do Teams](/teams-add-on-licensing/microsoft-teams-add-on-licensing.md).



## <a name="remove-a-license"></a>Remover uma licença

Se você tiver um usuário com um número de telefone atribuído e remover uma ou mais das licenças de pré-requisitos, a remoção da licença também desatribuirá o número de telefone do usuário. Sem um número de telefone atribuído, a capacidade do usuário de fazer e receber chamadas PSTN no Microsoft Teams é afetada.

Dependendo da [opção de conectividade PSTN](pstn-connectivity.md) do usuário, a remoção de uma licença tem o seguinte impacto nos parâmetros de telefonia:

- **A remoção de uma licença do Plano de Chamada Microsoft 365 de um usuário com um número de telefone do Plano de Chamada** será:
  - Copiar qualquer valor no OnPremLineUri para LineUri
  - Definir EnterpriseVoiceEnabled como False
  - Definir o status da atribuição de número de telefone como Unassigned no banco de dados de número de telefone


- **A remoção de uma licença Microsoft 365 do Sistema Telefônico de um usuário com um número de telefone do Operator Connect** será:
  - Limpar LineUri
  - Definir EnterpriseVoiceEnabled como False
  - Defina o status de atribuição do número de telefone como Unassigned no banco de dados de números de telefone


- **A remoção de uma licença Microsoft 365 do Sistema Telefônico de um usuário com um número de telefone de Roteamento Direto** será:
  - Limpar LineUri
  - Definir EnterpriseVoiceEnabled como False
  - Remover o número de telefone do banco de dados de números de telefone


## <a name="change-a-license"></a>Alterar uma licença

Se você precisar alterar uma licença para um usuário que envolve uma das licenças de pré-requisito, você deve garantir que as alterações de licenciamento sejam feitas e salvas ao mesmo tempo. Esse método garantirá que o usuário mantenha seu número de telefone atribuído e possa continuar fazendo e recebendo chamadas PSTN no Microsoft Teams. 

Por exemplo, suponha que você queira atribuir uma licença de Microsoft 365 E5 a um usuário que atualmente tem uma licença de Microsoft 365 E3. 

- Se você estiver usando o centro de administração do Teams, na guia **Licenças e aplicativos** nos detalhes do usuário, verifique se a licença antiga foi removida e a nova licença será adicionada antes de clicar em **Salvar alterações**. 

- Se você estiver usando os cmdlets do PowerShell, [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense) ou [Set-MgUserLicense](/powershell/module/microsoft.graph.users.actions/set-mguserlicense), execute o cmdlet uma vez e use os parâmetros -AddLicenses e -RemoveLicenses.

(Se você remover a licença antiga e salvar a alteração e adicionar a nova licença e salvar a alteração, o número de telefone não será atribuído e o usuário poderá perder a capacidade de fazer e receber chamadas PSTN no Microsoft Teams. Depois de atribuir a nova licença, você precisará atribuir novamente o número de telefone ao usuário.)

Para obter informações sobre como alterar a licença simultaneamente com o licenciamento baseado em grupo, consulte [Alterar atribuições de licença para um usuário ou grupo no Azure Active Directory](/azure/active-directory/enterprise-users/licensing-groups-change-licenses).
