---
title: Planejar conferência de Conexão operador
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.date: 10/28/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Saiba mais sobre a Conexão de operador, como requisitos e planejamento para implantação.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: d910fd9d464d1c4ff452da70a3bde039e4748123
ms.sourcegitcommit: be8b820caf4b5a1a91ad444ba93da1df20bf63ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2021
ms.locfileid: "61257496"
---
# <a name="plan-for-operator-connect-conferencing"></a>Planejar conferência de Conexão operador

A Audioconferência da Microsoft oferece a capacidade de discar em uma conferência e discar de uma conferência usando números de telefone PSTN (Rede Telefônica Pública Comutado).  Os participantes participam Microsoft Teams reuniões usando uma ponte de conferência somente áudio.

Com os recursos Conexão conferência de operador, as organizações podem usar números de telefone de uma operadora de terceiros para ingressar Microsoft Teams reuniões. Se sua operadora atual faz parte do programa Conexão microsoft operator, você pode adicionar números de telefone de sua operadora à sua ponte de Audioconferência e usá-los para participar de reuniões.

Sem os Conexão de Conferência de Operador, as organizações só podem usar números de telefone fornecidos pela Microsoft para sua ponte de audioconferência.

>[!NOTE]
>Um provedor de números de telefone que faz parte do programa de Conexão microsoft é referenciado neste artigo como um "operador".
>
>Para ver se o operador participa do programa de Conexão do Microsoft Operator, consulte o diretório [Microsoft 365 Operador Conexão .](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)

Este artigo descreve o operador Conexão Conferência:

- [Benefícios](#benefits)
- [Requisitos de licenciamento e cobrança](#licensing-requirements-and-billing)
- [Informações adicionais sobre a Audioconferência da Microsoft](#additional-information-on-microsoft-audio-conferencing)

Para obter informações sobre como configurar a Conferência Conexão Operador, consulte [Configure Operator Conexão Conferencing](operator-connect-conferencing-configure.md).

Se alguns dos usuários da sua organização precisam fazer chamadas externas para números de telefone PSTN, você ainda precisa de um plano de chamadas. Para saber mais sobre como usar um operador de [terceiros](operator-connect-plan.md)para conectividade PSTN externa, consulte Plan for Operator Conexão .

## <a name="benefits"></a>Benefícios

A Conexão conferência do operador oferece os seguintes benefícios:

- **Alocação flexível de números de telefone entre sua operadora e a Microsoft.** Use números de telefone da Microsoft e de sua operadora (somente com uma assinatura do Microsoft AudioConferência Standard) ou use apenas números de telefone de sua operadora (somente com uma licença de conferência Conexão Operador).

- **Infraestrutura gerenciada pelo operador.**   Seu operador gerencia os Controladores de Borda de Sessão (SBCs) e a interconexão com a Microsoft, salvando você de compras e gerenciamento de hardware extra.

- **Implantação mais rápida e fácil.**   Conecte-se rapidamente à sua operadora e atribua números de telefone à sua ponte de Audioconferência a partir do Teams de administração.

- **Suporte e confiabilidade aprimorados.**   Os operadores fornecem suporte técnico e contratos de nível de serviço compartilhados para melhorar o suporte ao serviço e o peering direto do Azure cria uma conexão de rede um para um para melhorar a confiabilidade.

A Conexão conferência de operadores pode ser a solução certa para sua organização se:

- Você deseja manter **seus contratos com** seu provedor de número de telefone existente

- Você deseja expandir **a cobertura global da** ponte de Audioconferência da Microsoft existente

- Você deseja **origem de números de telefone para Audioconferência** de um novo provedor de números de telefone

- **A Audioconferência da Microsoft não está disponível em sua localização geográfica**

- Você deseja aproveitar uma operadora para serviços de **Audioconferência** com um modelo de pagamento por minuto , como usar números de chamada gratuita e fazer chamadas de saída de reuniões de Teams para números de telefone em países não incluídos em sua assinatura

## <a name="licensing-requirements-and-billing"></a>Requisitos de licenciamento e cobrança

Os usuários que precisam de números de Conferência Conexão operador para ingressar nas reuniões que organizam devem ter uma assinatura Padrão de Audioconferência da Microsoft ou uma licença de Conferência do Microsoft Operator Conexão atribuída a eles.

### <a name="audio-conferencing-standard-subscription"></a>Assinatura Padrão de Audioconferência

Uma assinatura Do Microsoft AudioConferência Standard pode ser adquirida como um complemento para uma licença Microsoft Teams e também está incluída em assinaturas Microsoft 365 E5 e Office 365 E5.

A assinatura Padrão de Audioconferência permite que os assinantes usem números de telefone da Microsoft e expandam suas pontes de audioconferência com números de uma operadora. Os assinantes também podem decidir quais chamadas de saída de Teams reuniões para rotear por meio da Microsoft e quais chamadas encaminhar por meio de um operador.

Para obter mais informações, consulte [**Configure Operator Conexão Conferencing**](operator-connect-conferencing-configure.md).

### <a name="operator-connect-conferencing-license"></a>Licença de Conexão de conferência de operador

Uma licença Conexão de Conferência do Microsoft Operator pode ser adquirida como um complemento para uma Microsoft Teams de conferência.

A licença Conexão de Conferência de Operador permite que os assinantes usem números de telefone de uma operadora, mas ela não inclui números de telefone da Microsoft. Todas as chamadas de saída de Teams reuniões devem ser roteados por meio de um operador.

Para obter mais informações, consulte [**Configure Operator Conexão Conferencing**](operator-connect-conferencing-configure.md).

>[!Note]
>Os participantes da reunião não exigem uma licença de Assinatura Padrão de Audioconferência ou uma licença de Conferência Conexão Operador para ingressar em uma reunião organizada por um usuário com recursos de Conferência Conexão Operador.

Com a Conferência Conexão operador, a Microsoft fatura sua organização de acordo com o tipo de licença de Audioconferência usada pela sua organização, Conferência de Áudio da Microsoft ou Conferência Conexão Operador e o uso de todos os números de telefone fornecidos pela Microsoft.

Sua operadora cobra a sua organização pelo uso de operadores Conexão números de Conferência que eles fornecem.

## <a name="additional-information-on-microsoft-audio-conferencing"></a>Informações adicionais sobre a Audioconferência da Microsoft

A Audioconferência da Microsoft permite que os participantes participem Microsoft Teams reuniões discando com um número de telefone PSTN ou discando para um número de telefone PSTN. Para obter mais informações sobre os recursos de Audioconferência da Microsoft disponíveis para sua organização, consulte [Audioconferência em Microsoft 365](audio-conferencing-in-office-365.md).
