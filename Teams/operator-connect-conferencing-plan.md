---
title: Planejar para Conferência de conexão do operador
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
- highpri
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Saiba mais sobre Conferência de conexão do operador, como requisitos e planejamento para implantação.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9e1c363c66028a9e8611fa38179585e1e073c54b
ms.sourcegitcommit: cbcf37f395832bed871fe709b87c6eecb1fdfd72
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2022
ms.locfileid: "68583979"
---
# <a name="plan-for-operator-connect-conferencing"></a>Planejar para Conferência de conexão do operador

A Audioconferência da Microsoft fornece a capacidade de discar para uma conferência e discar de uma conferência usando números de telefone PSTN (Rede Telefônica Pública Comuada).  Os participantes ingressam em reuniões do Microsoft Teams usando uma ponte de conferência somente áudio.

Com Conferência de conexão do operador recursos, as organizações podem usar números de telefone de um operador de terceiros para ingressar em reuniões do Microsoft Teams. Se o operador atual fizer parte do programa Microsoft Operator Connect, você poderá adicionar números de telefone de sua operadora à ponte de Audioconferência e usá-los para ingressar em reuniões.

Sem Conferência de conexão do operador recursos, as organizações só podem usar números de telefone fornecidos pela Microsoft para sua ponte de audioconferência.

>[!NOTE]
>Um provedor de números de telefone que faz parte do programa Microsoft Operator Connect é referenciado neste artigo como um "operador".
>
>Para ver se o operador participa do programa Microsoft Operator Connect, consulte o [diretório Microsoft 365 Operator Connect](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory).

Este artigo descreve Conferência de conexão do operador:

- [Benefícios](#benefits)
- [Requisitos de licenciamento e cobrança](#licensing-requirements-and-billing)
- [Informações adicionais sobre a Audioconferência da Microsoft](#additional-information-on-microsoft-audio-conferencing)

Para obter informações sobre como Conferência de conexão do operador, consulte [Configurar Conferência de conexão do operador](operator-connect-conferencing-configure.md).

Se alguns dos usuários da sua organização precisam fazer chamadas externas para números de telefone PSTN, você ainda precisará de um plano de chamada. Para saber mais sobre como usar um operador de terceiros para conectividade PSTN externa, consulte [Plan for Operator Connect](operator-connect-plan.md).

## <a name="benefits"></a>Benefícios

Conferência de conexão do operador oferece os seguintes benefícios:

- **Alocação flexível de números de telefone entre sua operadora e a Microsoft.** Use números de telefone da Microsoft e de sua operadora (somente com uma assinatura Padrão de Audioconferência da Microsoft) ou use apenas números de telefone de sua operadora (somente com uma licença Conferência de conexão do operador serviço).

- **Infraestrutura gerenciada pelo operador.** Seu operador gerencia os controladores de borda de sessão (SBCs) e a interconectividade com a Microsoft, salvando você de compras e gerenciamento de hardware extras.

- **Implantação mais rápida e fácil.** Conecte-se rapidamente ao operador e atribua números de telefone à ponte de Audioconferência do centro de administração do Teams.

- **Suporte e confiabilidade aprimorados.** Os operadores fornecem suporte técnico e contratos de nível de serviço compartilhado para melhorar o suporte ao serviço, e o emparelhamento direto da plataforma Azure cria uma conexão de rede um-para-um para melhorar a confiabilidade.

Conferência de conexão do operador pode ser a solução certa para sua organização se:

- Você deseja manter **seus contratos com** seu provedor de número de telefone existente

- Você deseja expandir **a cobertura global da** ponte de Audioconferência da Microsoft existente

- Você deseja obter **números de telefone de origem para Audioconferência** de um novo provedor de números de telefone

- **A Audioconferência da Microsoft não está disponível em sua localização geográfica**

- Você deseja aproveitar um operador para serviços de **Audioconferência** com um modelo de pagamento por minuto, como usar números de chamada gratuita e fazer chamadas de saída de reuniões do Teams para números de telefone em países não incluídos em sua assinatura

## <a name="licensing-requirements-and-billing"></a>Requisitos de licenciamento e cobrança

Os usuários que precisam Conferência de conexão do operador para ingressar nas reuniões que organizam devem ter uma assinatura Padrão de Audioconferência da Microsoft ou uma licença do Microsoft Conferência de conexão do operador atribuída a eles.

### <a name="audio-conferencing-standard-subscription"></a>Assinatura Padrão de Audioconferência

Uma assinatura Padrão de Audioconferência da Microsoft pode ser adquirida como um complemento para uma licença do Microsoft Teams e também está incluída em Microsoft 365 E5 e Office 365 E5 assinaturas.

A assinatura Padrão de Audioconferência permite que os assinantes usem números de telefone da Microsoft e expandam suas pontes de audioconferência com números de um operador. Os assinantes também podem decidir quais chamadas de saída das reuniões do Teams serão roteadas pela Microsoft e quais chamadas rotear por meio de um operador.

Para obter mais informações, [**consulte Configurar Conferência de conexão do operador**](operator-connect-conferencing-configure.md).

### <a name="operator-connect-conferencing-license"></a>Conferência de conexão do operador licença

Uma licença Conferência de conexão do operador Microsoft pode ser adquirida como um complemento para uma licença do Microsoft Teams.

A Conferência de conexão do operador permite que os assinantes usem números de telefone de um operador, mas não inclui números de telefone da Microsoft. Todas as chamadas de saída de reuniões do Teams devem ser roteadas por meio de um operador.

Para obter mais informações, [**consulte Configurar Conferência de conexão do operador**](operator-connect-conferencing-configure.md).

>[!Note]
>Os participantes da reunião não exigem uma licença de Assinatura Padrão de Audioconferência ou uma licença Conferência de conexão do operador para ingressar em uma reunião organizada por um usuário com Conferência de conexão do operador recursos.

Com o Conferência de conexão do operador, a Microsoft cobra sua organização de acordo com o tipo de licença de Audioconferência usada pela sua organização, conferência de áudio da Microsoft ou Conferência de conexão do operador e o uso de qualquer número de telefone fornecido pela Microsoft.

Seu operador cobra a sua organização pelo uso de Conferência de conexão do operador números fornecidos.

## <a name="additional-information-on-microsoft-audio-conferencing"></a>Informações adicionais sobre a Audioconferência da Microsoft

A Audioconferência da Microsoft permite que os participantes participem de reuniões do Microsoft Teams discando com um número de telefone PSTN ou discando para um número de telefone PSTN. Para obter mais informações sobre os recursos de Audioconferência da Microsoft disponíveis para sua organização, consulte [Audioconferência no Microsoft 365](audio-conferencing-in-office-365.md).
