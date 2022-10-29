---
title: Atualizações do Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: annaray
search.appverid: MET150
f1.keywords:
- NOCSH
description: Neste artigo, você aprenderá sobre o processo de atualização do cliente de área de trabalho do Microsoft Teams.
ms.localizationpriority: high
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0aa6a64b799f3d00262ab8a086d477bda482ac40
ms.sourcegitcommit: e6182aa3b15346dc955333a2bc571565ef463a57
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2022
ms.locfileid: "68784146"
---
# <a name="teams-update-process"></a>Processo de atualização do Teams

As atualizações do aplicativo Web do Teams geralmente são lançadas na 4ª segunda-feira de cada mês.

As atualizações do cliente de área de trabalho do Teams são lançadas mensalmente após rigorosos testes internos e validação por meio de nosso Programa de Adoção de Tecnologia (TAP). As atualizações do cliente de área de trabalho geralmente começam na 4ª segunda-feira do mês e são distribuídas gradualmente para os clientes durante o restante da semana. Se uma atualização crítica for necessária, o Teams ignorará essa programação e lançará a atualização assim que estiver disponível.

The desktop client updates itself automatically. Teams checks for updates every few hours behind the scenes, downloads it, and then waits for the computer to be idle before silently installing the update.

Os usuários também podem baixar atualizações manualmente selecionando **Verificar atualizações** no menu suspenso **...** ao lado do ícone **Perfil** no canto superior direito do aplicativo. Se houver uma atualização disponível, ela será baixada e instalada silenciosamente quando o computador estiver ocioso.

Os usuários precisam estar logados para que as atualizações sejam baixadas.

## <a name="what-about-updates-to-microsoft-365-apps-for-enterprise"></a>E quanto às atualizações para o Microsoft 365 Apps para Grandes Empresas?

O Teams é instalado por padrão com as novas instalações do Microsoft 365 Apps para Grandes Empresas, conforme descrito em [Implantar o Microsoft Teams com o Microsoft 365 Apps para Grandes Empresas](/DeployOffice/teams-install).

O Teams segue seu próprio processo de atualização, conforme descrito acima. O Teams não segue o processo de atualização para os outros aplicativos do Office, como Word e Excel. Para saber mais, leia [Visão geral dos canais de atualização do Microsoft 365 Apps](/DeployOffice/overview-update-channels).

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>Os administradores podem implantar as atualizações em vez da atualização automática do Teams?

O Teams não dá aos administradores a capacidade de implantar atualizações por meio de qualquer mecanismo de entrega.

## <a name="servicing-agreement"></a>Contrato de manutenção

Como parte de um serviço online moderno, o cliente do Teams é atualizado aproximadamente uma vez por mês. O cliente instala automaticamente as atualizações quando elas ficam disponíveis para esse cliente. Como escalonamos a disponibilidade de atualizações em todo o mundo, alguns clientes em sua organização podem receber novas atualizações antes de outros. Como o Teams é regido pela Política de Ciclo de Vida Moderna, espera-se que os usuários permaneçam com a versão mais atualizada do cliente de área de trabalho. As atualizações automáticas garantem que os usuários tenham os mais recentes recursos, aprimoramentos de desempenho, segurança e confiabilidade de serviço.

Para identificar quando os clientes de área de trabalho ficam desatualizados, um alerta no aplicativo será exibido se a versão atual do usuário tiver entre um e três meses e se houver uma nova versão disponível. Isso nas mensagens no aplicativo incentiva os usuários a atualizarem para a versão mais recente do Teams ou, se necessário, entrar em contato com o administrador de TI para fazer isso. Os usuários de clientes de área de trabalho do Teams com mais de três meses verão uma página de bloqueio que oferece a opção de atualizar agora, entrar em contato com o administrador de TI ou continuar com o Teams na web.

Os clientes de área de trabalho do Teams em Nuvens Governamentais atualmente têm uma exceção a este contrato de serviço até novo aviso.

Para obter informações sobre os lançamentos de novas versões, verifique a [Centro de Mensagens](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) ou vá para a **Ajuda** > **Novidades** no cliente.

## <a name="what-about-updates-to-teams-on-vdi"></a>E as atualizações para o Teams na VDI?

Os clientes do Teams na Infraestrutura de Área de trabalho Virtual (VDI) não são atualizados automaticamente da mesma maneira que os clientes não VDI do Teams. Você deve atualizar a imagem da VM instalando um novo MSI conforme descrito nas instruções para [Instalar o Teams na VDI](teams-for-vdi.md). Você deve desinstalar a versão atual para atualizar para uma versão mais recente.
