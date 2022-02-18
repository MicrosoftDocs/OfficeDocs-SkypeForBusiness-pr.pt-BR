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
description: Neste artigo, você aprenderá sobre o processo de atualização do cliente de área de trabalho do Microsoft Teams.
ms.localizationpriority: high
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 65421d36c0a8c19d8c7118e348222e3b62175a95
ms.sourcegitcommit: a9a056b93b4add3a4d978bb341ea4b66a042b4d0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2022
ms.locfileid: "62893520"
---
# <a name="teams-update-process"></a>Processo de atualização do Teams

O aplicativo Web do Teams é atualizado semanalmente.

As atualizações do cliente de área de trabalho do Teams são lançadas a cada duas semanas após rigorosos testes internos e validação por meio de nosso Programa de Adoção de Tecnologia (TAP). A atualização geralmente ocorre em uma Terça-feira. Se uma atualização crítica for necessária, o Teams ignorará essa programação e lançará a atualização assim que estiver disponível.

O cliente da área de trabalho se atualiza automaticamente. O Teams verifica se há atualizações a cada algumas horas nos bastidores, baixa-as e aguarda até que o computador esteja ocioso antes de instalar silenciosamente a atualização.

Os usuários também podem baixar atualizações manualmente selecionando **Verificar atualizações** no menu suspenso **...** ao lado do ícone **Perfil** no canto superior direito do aplicativo. Se houver uma atualização disponível, ela será baixada e instalada silenciosamente quando o computador estiver ocioso.

Os usuários precisam estar logados para que as atualizações sejam baixadas.

## <a name="what-about-updates-to-microsoft-365-apps-for-enterprise"></a>E quanto às atualizações para o Microsoft 365 Apps para Grandes Empresas?

O Teams é instalado por padrão com as novas instalações do Microsoft 365 Apps para Grandes Empresas, conforme descrito em [Implantar o Microsoft Teams com o Microsoft 365 Apps para Grandes Empresas](/DeployOffice/teams-install).

O Teams segue seu próprio processo de atualização, conforme descrito acima. O Teams não segue o processo de atualização para os outros aplicativos do Office, como Word e Excel. Para saber mais, leia [Visão geral dos canais de atualização do Microsoft 365 Apps](/DeployOffice/overview-update-channels).

## <a name="what-about-updates-to-teams-on-vdi"></a>E as atualizações para o Teams na VDI?


Os clientes do Teams na Infraestrutura de Área de trabalho Virtual (VDI) não são atualizados automaticamente da mesma maneira que os clientes não VDI do Teams. Você deve atualizar a imagem da VM instalando um novo MSI conforme descrito nas instruções para [Instalar o Teams na VDI](teams-for-vdi.md). Você deve desinstalar a versão atual para atualizar para uma versão mais recente.

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>Os administradores podem implantar as atualizações em vez da atualização automática do Teams?

O Teams não dá aos administradores a capacidade de implantar atualizações por meio de qualquer mecanismo de entrega.

## <a name="servicing-agreement"></a>Contrato de manutenção

Como um serviço online moderno, o cliente do Teams é atualizado automaticamente a cada duas semanas. Como o Teams é regido pela Política de Ciclo de Vida Moderna, espera-se que os usuários permaneçam com a versão mais atualizada do cliente de área de trabalho. As atualizações automáticas garantem que os usuários tenham os mais recentes recursos, aprimoramentos de desempenho, segurança e confiabilidade de serviço.

Para identificar quando os clientes de área de trabalho ficam desatualizados, um alerta no aplicativo será exibido se a versão atual do usuário tiver entre um e três meses e se houver uma nova versão disponível. Isso nas mensagens no aplicativo incentiva os usuários a atualizarem para a versão mais recente do Teams ou, se necessário, entrar em contato com o administrador de TI para fazer isso. Os usuários de clientes de área de trabalho do Teams com mais de três meses verão uma página de bloqueio que oferece a opção de atualizar agora, entrar em contato com o administrador de TI ou continuar com o Teams na web.

Os clientes de área de trabalho do Teams em Nuvens Governamentais atualmente têm uma exceção a este contrato de serviço até novo aviso.

Para obter informações sobre os lançamentos de novas versões, verifique a [Centro de Mensagens](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) ou vá para a **Ajuda** > **Novidades** no cliente.
