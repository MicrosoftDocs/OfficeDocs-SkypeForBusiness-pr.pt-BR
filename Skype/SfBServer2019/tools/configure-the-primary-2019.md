---
title: Configurar o servidor de gerenciamento principal
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: 'Resumo: configure seu servidor de gerenciamento principal, instale o System Center Operations Manager e importe pacotes de gerenciamento para Skype for Business Server 2019.'
ms.openlocfilehash: 8dd5b3ff94f393ccce88dd5a27bd8133810b4c1c
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60760339"
---
# <a name="skype-for-business-server-configure-the-primary-management-server"></a>Skype for Business Server: Configurar o servidor de gerenciamento principal

**Resumo:** Configure seu servidor de gerenciamento principal, instale System Center Operations Manager e importe pacotes de gerenciamento para Skype for Business Server 2019.

Para aproveitar ao máximo os novos recursos de monitoramento de saúde incluídos no Skype for Business Server 2019, você deve primeiro designar um computador para atuar como seu servidor de gerenciamento principal. Em seguida, você deve instalar o System Center Operations Manager 2012 SP1 ou R2 ou System Center Operations Manager 2007 R2 nesse computador. Além disso, você deve primeiro instalar uma versão com suporte do SQL Server para funcionar como seu banco de dados back-end do Operations Manager.

Ao instalar o System Center Operations Manager, você precisará instalar todos os componentes desse produto, incluindo:

- Banco de dados operacional

- Servidor

- Console

- \s-1 \plain Windows PowerShellcmdlets

- Console da Web

- Reporting

- Data warehouse

> [!IMPORTANT]
> O Microsoft Report Viewer pacote redistribuível 2010 deve ser instalado antes de instalar o System Center Operations Manager 2012.

Para obter detalhes sobre esses produtos e sua instalação, [consulte System Center Operations Manager 2012](/previous-versions/system-center/system-center-2012-R2/hh205987(v=sc.12))

Lembre-se de que você pode ter apenas um Servidor de Gerenciamento Raiz por Skype for Business Server implantação.

## <a name="importing-the-skype-for-business-server-2019-management-packs"></a>Importando os pacotes de gerenciamento Skype for Business Server 2019

Você pode estender os recursos do System Center Operations Manager instalando pacotes de gerenciamento, software que determina quais itens o System Center Operations Manager pode monitorar, como esses itens devem ser monitorados e como os alertas devem ser disparados e relatados. Skype for Business Server 2019 inclui dois pacotes de gerenciamento do Operations Manager System Center que fornecem os seguintes recursos:

- O **Component and User Management Pack** (Microsoft.LS.2019.Monitoring.ComponentAndUser.mp) rastreia Skype for Business Server problemas registrados em logs de eventos, registrados por contadores de desempenho ou registrados nos cdrs (registros de detalhes da chamada) ou nos bancos de dados de Qualidade da Experiência (QoE). Para problemas críticos, System Center Operations Manager pode ser configurado para notificar imediatamente os administradores por email, mensagem instantânea ou mensagens SMS. (SMS, ou Serviço de Mensagem Curta, é a tecnologia usada para enviar mensagens de texto de um dispositivo móvel para outro.)

    > [!NOTE]
    >  Para obter detalhes sobre como configurar a notificação do Operations Manager, consulte [Configuring Notification](/previous-versions/system-center/operations-manager-2007-r2/dd440890(v=technet.10)).

- O **Active Monitoring Management Pack** (Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp) testa proativamente os principais componentes Skype for Business Server, como entrar no sistema, trocar mensagens instantâneas ou fazer chamadas para um telefone localizado na PSTN (rede telefônica pública comutado). Esses testes são conduzidos usando os cmdlets Skype for Business Server transações sintéticas. Por exemplo, o cmdlet **Test-CsIM** é usado para simular uma conversa de mensagem instantânea entre um par de usuários de teste. Se essa conversa simulada falhar, um alerta será gerado.

Importar os pacotes de gerenciamento é uma etapa crucial. Se os pacotes de gerenciamento não são importados, você não poderá usar o Operations Manager para monitorar Skype for Business Server eventos ou executar Skype for Business Server transações sintéticas.

O Component and User Management Pack é usado para monitorar somente Skype for Business Server 2019. Se você estiver em um cenário de coexistência em que o Skype for Business Server 2019 e o Skype for Business Server 2015 estão instalados, você deve continuar a usar os pacotes de gerenciamento do Skype for Business Server 2015 para seus computadores Skype for Business Server 2015.

> [!NOTE]
> Os pacotes de gerenciamento do Skype for Business Server 2019 incluem o componente Skype for Business Server 2019 e o User Management Pack e o Skype for Business Server 2019 Active Monitoring Management Pack.

Você pode usar uma destas ferramentas para importar pacotes de gerenciamento:

- **System Center Operations Manager** Com esse método, você usa o Operations Manager para adicionar monitoramento para Skype for Business Server.

- **Shell do Operations Manager** Você pode usar o Shell do Operations Manager para importar diretamente ou solucionar problemas que encontrar ao importar pacotes de gerenciamento usando o console do System Center Operations Manager.

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>Importando os Pacotes de Gerenciamento usando o System Center Operations Manager

1. Baixe o SkypeForBusiness2019ManagementPacks.msi dos downloads da Microsoft Web e instale o msi.

2. No System Center Operations Manager, clique em **Administração**.

3. No painel Administração, clique com o botão direito do mouse em **Pacotes de gerenciamento** e, em seguida, clique em **Importar pacotes de gerenciamento**.

4. Na caixa de diálogo **Selecinar pacotes de gerenciamento**, clique em **Adicionar** e, em seguida, em **Adicionar do disco**.

5. Na caixa **de diálogo Conexão de** Catálogo Online, clique em **Não**.

6. Na caixa de diálogo Selecionar Pacotes de Gerenciamento a serem **importados,** localize e selecione os arquivos Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp e Microsoft.LS.2019.Monitoring.ComponentAndUser.mp e clique em **Abrir**. Para selecionar vários arquivos na caixa de diálogo, clique no primeiro arquivo e segure a tecla Ctrl e clique nos arquivos subsequentes.

7. Na caixa de seleção **Selecionar pacotes de gerenciamento**, clique em **Instalar**. Se receber uma mensagem de erro e a instalação falhar, geralmente isso signfica que os arquivos dos pacotes de gerenciamento estão em uma pasta protegida pelo Controle de conta de usuário do Windows. Se isso ocorrer, copie os arquivos para uma pasta diferente e reinicie o processo de importação e instalação.

8. Na caixa de diálogo **Selecionar pacotes de gerenciamento**, clique em **Fechar**. O processo de importação e instalação pode exigir vários minutos para ser concluído.

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a>Importando os Pacotes de Gerenciamento usando o Shell do Operations Manager

Em geral, é mais fácil importar os pacotes de gerenciamento usando o console do Operations Manager. No entanto, se ocorrer um erro e a importação falhar, o console nem sempre fornecerá relatórios de erros adequados. Por comparação, o Shell do Operations Manager fornece informações detalhadas. Se você estiver usando o Operations Manager e encontrar problemas ao importar um pacote de gerenciamento, importe o pacote usando o Shell do Operations Manager. As informações fornecidas pelo Shell do Operations Manager podem ajudá-lo a determinar por que a importação falhou.

1. Clique **em Iniciar,** em **Todos os Programas,** em **Microsoft System Center 2012,** em **Operations Manager** e em **Shell do Operations Manager**.

2. Em Shell do Operations Manager, digite o seguinte comando no prompt de comando, usando o caminho real para sua cópia do arquivo Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp e pressione ENTER:

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp"
   ```

3. Depois de importar o primeiro pacote de gerenciamento, repita o processo, usando o caminho para sua cópia do arquivo Microsoft.LS.2019.Monitoring.ComponentAndUser.mp:

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ComponentAndUser.mp"
   ```