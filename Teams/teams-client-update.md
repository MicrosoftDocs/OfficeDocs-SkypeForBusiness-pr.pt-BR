---
title: Atualizações do Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: annaray
search.appverid: MET150
f1.keywords:
- NOCSH
description: Neste artigo, você aprenderá sobre o processo por trás da atualização do cliente de área de trabalho do Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 68e26325f4efcc5ffd7731b73e397f1f96579dd5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119240"
---
# <a name="teams-update-process"></a>Processo de atualização do Teams

O aplicativo Web do Teams é atualizado semanalmente.

As atualizações do cliente da área de trabalho do Teams são lançadas a cada duas semanas após testes e validações internos rigorosos por meio do nosso Programa de Adoção de Tecnologia (TAP). A atualização geralmente ocorre em uma terça-feira. Se uma atualização crítica for necessária, o Teams ignorará esse cronograma e liberará a atualização assim que estiver disponível.

O cliente da área de trabalho se atualiza automaticamente. O Teams verifica atualizações a cada poucas horas nos bastidores, baixa-as e aguarda o computador ficar ocioso antes de instalar silenciosamente a atualização.

Os usuários também podem baixar as atualizações manualmente selecionando **Verificar** se há atualizações no menu suspenso Perfil no canto superior direito do aplicativo.  Se uma atualização estiver disponível, ela será baixada e instalada silenciosamente quando o computador estiver ocioso.

Os usuários precisam estar assinados para que as atualizações sejam baixadas.

A partir de 31 de julho de 2019, as atualizações de cliente do Teams usam menor largura de banda de rede durante a atualização. Essa atualização está 100% ativas por padrão e não requer nenhuma ação de administradores ou usuários.

## <a name="what-about-updates-to-microsoft-365-apps-for-enterprise"></a>E as atualizações do Microsoft 365 Apps para empresas?

O Teams é instalado por padrão com novas instalações do Microsoft 365 Apps para empresas, conforme descrito em [Deploy Microsoft Teams with Microsoft 365 Apps for enterprise](/DeployOffice/teams-install).

O Teams segue seu próprio processo de atualização conforme descrito acima. O Teams não segue o processo de atualização para outros aplicativos de Escritórios, como Word e Excel. Para saber mais, leia [Visão geral dos canais de atualização do Microsoft 365 Apps para empresas](/DeployOffice/overview-of-update-channels-for-office-365-proplus)

## <a name="what-about-updates-to-teams-on-vdi"></a>E as atualizações do Teams no VDI?


Os clientes do Teams Virtual Desktop Infrastructure (VDI) não são atualizados automaticamente da maneira que os clientes do Teams não VDI são. Você precisa atualizar a imagem da VM instalando um novo MSI conforme descrito nas instruções para Instalar o [Teams na VDI](teams-for-vdi.md). Você deve desinstalar a versão atual para atualizar para uma versão mais recente.

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>Os administradores podem implantar atualizações em vez da atualização automática do Teams?

O Teams não dá aos administradores a capacidade de implantar atualizações por meio de qualquer mecanismo de entrega.

## <a name="servicing-agreement"></a>Contrato de manutenção

Como um serviço online moderno, o cliente teams atualiza automaticamente a cada duas semanas. Como o Teams é governado pela Política de Ciclo de Vida Moderna, é esperado que os usuários permaneçam na versão mais atualizada do cliente da área de trabalho. As atualizações automáticas garantem que os usuários tenham os recursos mais recentes, aprimoramentos de desempenho, segurança e confiabilidade do serviço.

Para identificar quando os clientes da área de trabalho não estão atualizados, um alerta no aplicativo será exibido se a versão atual do usuário tiver entre um e três meses e se houver uma nova versão disponível. Essa mensagem no aplicativo incentiva os usuários a atualizarem para a versão mais recente do Teams ou, se necessário, a entrar em contato com o administrador de IT para fazer isso. Os usuários em clientes de área de trabalho do Teams que têm mais de três meses verão uma página de bloqueio que oferece as opções de atualização agora, entre em contato com o administrador de IT ou continue com o Teams na Web.

As versões do cliente da área de trabalho com mais de três meses após a primeira instalação e/ou a primeira versão do Teams têm um período de carência de 28 dias antes de encontrar as informações de manutenção mencionadas acima. Durante esse período, o processo de atualização automática atualizará o cliente do Teams. Se não for atualizado, os usuários verão um alerta no aplicativo incentivando-os a atualizar manualmente para a versão mais recente do Teams. Os usuários podem ser solicitados a entrar em contato com o administrador de IT para fazer a atualização. Isso inclui os usuários que usam o cliente de área de trabalho do Teams como parte do pacote aplicativos do Microsoft 365 para empresas.

Os clientes de área de trabalho do Teams em Nuvens de Governo atualmente têm uma exceção para esse contrato de manutenção até aviso prévio.

Para obter informações sobre novas versões, verifique o [Centro](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) de Mensagens ou vá para **Ajudar**  >  **Novidades** no cliente.
