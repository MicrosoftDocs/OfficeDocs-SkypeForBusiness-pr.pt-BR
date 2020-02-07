---
title: Lista de verificação de integração para configurar a rede do Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Siga as tarefas principais, tarefas pendentes e atividades desta lista de verificação quando configurar sua rede para o Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 489857d1109230339a051712db374040800275fd
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41835951"
---
# <a name="configure-networking"></a>Configurar a rede

| Não | Atividade ou tarefa | Descrição | Concluído? | Informações adicionais |
|----|--------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | Revisar os requisitos de rede para equipes | Tenha uma visão geral dos requisitos de sua rede antes de entrar nos detalhes da rede. | | [Preparar a rede da organização para o Microsoft Teams](https://docs.microsoft.com/microsoftteams/prepare-network)                                                               |
| 2  | Fornecer o workshop de preparação de rede | Realize uma avaliação de preparação da rede. | |  |
| 3  | Usar o planejador de rede | Executar o planejamento de largura de banda de rede. | | |
| 4  | Validar o tamanho do pool NAT necessário para a conectividade do usuário | Certifique-se de que os endereços IP públicos adequados sejam atribuídos aos pools de NAT para evitar a exaustão de portabilidade. A exaustão da porta contribuirá para que os usuários internos e dispositivos não consigam se conectar ao serviço do Office 365. <br/><br/>Problemas de conectividade são uma causa principal dos problemas de percepção do usuário para serviços de nuvem. | | [Suporte a NAT com o Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9) |
| 5  | Implementar o roteamento mais eficiente para os datacenters da Microsoft | Identifique locais que podem usar pontos de saída locais ou regionais para se conectar à rede Microsoft da maneira mais eficiente possível. <br/><br/>O artigo na coluna **informações adicionais** descreve como os clientes podem tirar proveito dos recursos na resolução de nomes do Office 365 e no roteamento IP para se conectar eficientemente ao datacenter regional mais próximo. | | [Conectividade de cliente do Office 365](https://support.office.com/article/Client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b) |
| 6  | Configurar portas de firewall solicitadas para conectividade com o Microsoft Teams | Revise as URLs e IPs do Office 365 para identificar e testar as portas de firewall necessárias para conectividade entre clientes e servidores locais e serviços do Office 365. <br/><br/>Para um ambiente compatível, você deve abrir todas as portas nos seus firewalls. Deixar de abrir algumas portas ou intervalos afetará negativamente a experiência do usuário. Configure portas de mídia nos seus firewalls com base na orientação da coluna **informações adicionais** . | | [Endereços IP e URLs do Office 365 – Microsoft Teams](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) |
| 7  | Configurar servidores proxy | Configure seu ambiente para que os servidores proxy sejam ignorados e você possa conectar os usuários diretamente ao Office 365 usando o UDP para obter a melhor qualidade de áudio e vídeo. Quando mídias em tempo real são forçadas a atravessar um servidor proxy, a pilha de mídia no Teams é forçada a fazer failback para TCP, o que afeta negativamente a qualidade. <br/><br/>Para a experiência do usuário de qualidade mais alta, sempre prefira UDP sobre TCP. | | [Planejando o gerenciamento e a qualidade do serviço](https://docs.microsoft.com/MicrosoftTeams/envision-planning-for-service-management-and-quality-complete-guide) |
| 8  | Configurar a VPN de túnel dividido | Recomendamos que você forneça um caminho alternativo para o tráfego do teams que ignora a VPN, comumente conhecida como *VPN de encapsulamento de divisão*. Tunelamento dividido significa que o tráfego do Office 365 não percorrerá a VPN, mas vai diretamente para o Office 365. Essa alteração tem um impacto positivo sobre a qualidade, mas também apresenta um benefício secundário de reduzir a carga dos dispositivos de VPN e da rede da organização. | | Para implementar uma VPN de encapsulamento dividido, consulte o seu fornecedor de VPN para obter detalhes de configuração. |
| 9  | Configurar a priorização de pacotes usando QoS | A QoS deve ser implementada em todos os segmentos de uma rede gerenciada. Mesmo quando uma rede tem sido provisionada de forma adequada para largura de banda, a QoS permite a mitigação de risco no caso de eventos de rede não esperados. Quando a QoS é implementada, o tráfego de voz é priorizado para que esses eventos desprevistos não afetem negativamente a qualidade. | | [Planejando o gerenciamento e a qualidade do serviço](https://docs.microsoft.com/MicrosoftTeams/envision-planning-for-service-management-and-quality-complete-guide) <br/><br/>[Qualidade de Serviço no Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams) |
| 254 | Otimizar redes Wi-Fi para qualidade e desempenho | Vários fatores entram em cena quando você otimiza a sua rede Wi-Fi: <ul><li>Implementação de QoS ou de multimídia Wi-Fi (WMM) para garantir que o tráfego de mídia nas redes Wi-Fi seja priorizado.</li><li>Planejar e otimizar faixas de Wi-Fi e posicionamento de ponto de acesso. A faixa de 2,4 GHz pode oferecer desempenho adequado, dependendo do posicionamento do ponto de acesso.</li></ul> Consulte o fornecedor de Wi-Fi para obter orientação específica. | | [Recomendações de Wi-Fi para pontos de extremidade](https://docs.microsoft.com/MicrosoftTeams/envision-planning-for-service-management-and-quality-complete-guide#wi-fi-recommendations-for-endpoints) |
| 11:00 | Validar a conectividade de rede usando a ferramenta de avaliação de rede | Use a ferramenta de avaliação de rede para o Skype for Business e o Teams para testar a conectividade de todos os endereços IP e portas usados no Skype for Business Online e em chamadas e reuniões do teams. Baixe a ferramenta e veja o usage. docx para obter detalhes sobre como usar a ferramenta e interpretar os resultados do teste. Recomendamos que você execute a ferramenta a partir de um computador cliente em cada local em que as equipes serão usadas. | | [Ferramenta de avaliação de rede do Skype for Business e do teams](https://go.microsoft.com/fwlink/?linkid=855799) |
