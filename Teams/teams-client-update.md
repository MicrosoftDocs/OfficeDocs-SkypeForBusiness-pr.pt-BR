---
title: Teams atualizações
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
description: Neste artigo, você aprenderá sobre o processo por trás da atualização do cliente Microsoft Teams desktop.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 004c615d2b624f4e5942562e6abfed6e1aebf7cd
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/02/2021
ms.locfileid: "52717892"
---
# <a name="teams-update-process"></a>Teams processo de atualização

O Teams Web é atualizado semanalmente.

Teams de cliente da área de trabalho são lançadas a cada duas semanas após testes e validações internos rigorosos por meio do nosso Programa de Adoção de Tecnologia (TAP). A atualização geralmente ocorre em uma terça-feira. Se uma atualização crítica for necessária, Teams ignorará esse cronograma e liberará a atualização assim que estiver disponível.

O cliente da área de trabalho se atualiza automaticamente. Teams verifica se há atualizações a cada poucas horas nos bastidores, baixa-as e aguarda o computador ficar ocioso antes de instalar silenciosamente a atualização.

Os usuários também podem baixar as atualizações manualmente selecionando **Verificar** se há atualizações no menu suspenso Perfil no canto superior direito do aplicativo.  Se uma atualização estiver disponível, ela será baixada e instalada silenciosamente quando o computador estiver ocioso.

Os usuários precisam estar assinados para que as atualizações sejam baixadas.

A partir de 31 de julho de 2019, Teams de cliente usam menor largura de banda de rede durante a atualização. Essa atualização está 100% ativas por padrão e não requer nenhuma ação de administradores ou usuários.

## <a name="what-about-updates-to-microsoft-365-apps-for-enterprise"></a>E as atualizações para Microsoft 365 Apps para Grandes Empresas?

Teams é instalado por padrão com novas instalações de Microsoft 365 Apps para Grandes Empresas conforme descrito em [Deploy Microsoft Teams with Microsoft 365 Apps para Grandes Empresas](/DeployOffice/teams-install).

Teams segue seu próprio processo de atualização conforme descrito acima. Teams segue o processo de atualização para outros aplicativos de Escritórios, como Word e Excel. Para saber mais, leia [Visão geral dos canais de atualização para Microsoft 365 Apps para Grandes Empresas](/DeployOffice/overview-of-update-channels-for-office-365-proplus)

## <a name="what-about-updates-to-teams-on-vdi"></a>E as atualizações para Teams no VDI?


Teams clientes no Virtual Desktop Infrastructure (VDI) não são atualizados automaticamente da maneira que os clientes que não Teams VDI são. Você precisa atualizar a imagem da VM instalando um novo MSI conforme descrito nas instruções para Instalar Teams [VDI](teams-for-vdi.md). Você deve desinstalar a versão atual para atualizar para uma versão mais recente.

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>Os administradores podem implantar atualizações em vez de Teams atualização automática?

Teams não dá aos administradores a capacidade de implantar atualizações por meio de qualquer mecanismo de entrega.

## <a name="servicing-agreement"></a>Contrato de manutenção

Como um serviço online moderno, o Teams cliente atualiza automaticamente a cada duas semanas. Como Teams é governada pela Política de Ciclo de Vida Moderna, é esperado que os usuários permaneçam na versão mais atualizada do cliente da área de trabalho. As atualizações automáticas garantem que os usuários tenham os recursos mais recentes, aprimoramentos de desempenho, segurança e confiabilidade do serviço.

Para identificar quando os clientes da área de trabalho não estão atualizados, um alerta no aplicativo será exibido se a versão atual do usuário tiver entre um e três meses e se houver uma nova versão disponível. Essa mensagem no aplicativo incentiva os usuários a atualizarem para a versão mais recente do Teams ou, se necessário, para entrar em contato com o administrador de IT para fazer isso. Os usuários Teams clientes de área de trabalho com mais de três meses verão uma página de bloqueio que oferece as opções para atualizar agora, falar com o administrador de IT ou continuar a Teams na Web.

Teams clientes de área de trabalho em Nuvens de Governo atualmente têm uma exceção para esse contrato de manutenção até aviso prévio.

Para obter informações sobre novas versões, verifique o [Centro](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) de Mensagens ou vá para **Ajudar**  >  **Novidades** no cliente.
