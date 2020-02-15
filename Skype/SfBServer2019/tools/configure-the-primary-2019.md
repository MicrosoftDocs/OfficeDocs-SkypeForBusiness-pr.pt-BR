---
title: Configurar o servidor de gerenciamento principal
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumo: configure seu servidor de gerenciamento principal, instale o System Center Operations Manager e importe pacotes de gerenciamento para o Skype for Business Server 2019.'
ms.openlocfilehash: ccc522da216b98e6f18ea381a74aff19fc5cc24d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006046"
---
# <a name="configure-the-primary-management-server"></a>Configurar o servidor de gerenciamento principal

**Resumo:** Configure seu servidor de gerenciamento principal, instale o System Center Operations Manager e importe pacotes de gerenciamento para o Skype for Business Server 2019.

Para aproveitar ao máximo os novos recursos de monitoramento de integridade incluídos no Skype for Business Server 2019, você deve primeiro designar um computador para atuar como servidor de gerenciamento principal. Você deve instalar o System Center Operations Manager 2012 SP1 ou R2 ou System Center Operations Manager 2007 R2 no computador. Além disso, você deve primeiro instalar uma versão com suporte do SQL Server para funcionar como o banco de dados back-end do Operations Manager.

Ao instalar o System Center Operations Manager, será necessário instalar todos os componentes desse produto, incluindo:

- Banco de dados operacional

- Servidor

- Console

- \s-1 \plain Windows PowerShellcmdlets

- Console da Web

- Reporting

- Data warehouse

> [!IMPORTANT]
> O "[pacote redistribuível do Microsoft Report Viewer 2010](https://www.microsoft.com/download/details.aspx?id=6442)" precisa ser instalado antes da instalação do System Center Operations Manager 2012.

Para obter detalhes sobre esses produtos e sua instalação, consulte os seguintes links:

- [System Center Operations Manager 2012](https://go.microsoft.com/fwlink/p/?linkid=257527)

- [System Center Operations Manager 2007](https://technet.microsoft.com/library/bb735860.aspx)

Tenha em mente que você só pode ter um servidor de gerenciamento raiz por implantação do Skype for Business Server.

## <a name="importing-the-skype-for-business-server-2019-management-packs"></a>Importando os pacotes de gerenciamento do Skype for Business Server 2019

Você pode estender os recursos do System Center Operations Manager Instalando pacotes de gerenciamento — software que determina quais itens o System Center Operations Manager pode monitorar, como esses itens devem ser monitorados e como os alertas devem ser acionados e informação. O Skype for Business Server 2019 inclui dois pacotes de gerenciamento do System Center Operations Manager que oferecem os seguintes recursos:

- **O pacote de gerenciamento de componente e usuário** (Microsoft.ls.2019.Monitoring.ComponentAndUser.mp) rastreia problemas do Skype for Business Server registrados em logs de eventos, registrados por contadores de desempenho ou registrados nos registros de detalhes da chamada (CDRs) ou nos bancos de dados de QoE (qualidade da experiência). Para problemas críticos, o System Center Operations Manager pode ser configurado para notificar imediatamente os administradores por email, mensagem instantânea ou mensagens SMS. (SMS ou Short Message Service é a tecnologia usada para enviar mensagens de texto de um dispositivo móvel para outro).

    > [!NOTE]
    >  Para obter detalhes sobre como configurar a notificação do Operations Manager, consulte [Configuring Notification](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409).

- **O pacote de gerenciamento de monitoramento ativo** (Microsoft.ls.2019.Monitoring.ActiveMonitoring.mp) testa proativamente os principais componentes do Skype for Business Server, como entrar no sistema, trocar mensagens instantâneas ou fazer chamadas para um telefone localizado na rede telefônica pública comutada (PSTN). Esses testes são conduzidos usando os cmdlets de transação sintético do Skype for Business Server. Por exemplo, o cmdlet **Test-CsIM** é usado para simular uma conversa de mensagem instantânea entre um par de usuários de teste. Se essa conversa simulada falhar, um alerta será gerado.

A importação dos pacotes de gerenciamento é uma etapa crucial. Se os pacotes de gerenciamento não forem importados, você não poderá usar o Operations Manager para monitorar eventos do Skype for Business Server ou executar transações sintéticas do Skype for Business Server.

O pacote de gerenciamento de componente e usuário é usado para monitorar apenas o Skype for Business Server 2019. Se você estiver em um cenário de coexistência onde o Skype for Business Server 2019 e o Skype for Business Server 2015 estão instalados, você deve continuar a usar os pacotes de gerenciamento do Skype for Business Server 2015 para seus computadores com o Skype for Business Server 2015.

> [!NOTE]
> Os pacotes de gerenciamento para o Skype for Business Server 2019 incluem o componente e o pacote de gerenciamento do usuário do Skype for Business Server 2019 e o pacote de gerenciamento de monitoramento ativo do Skype for Business Server 2019.

Você pode usar uma destas ferramentas para importar pacotes de gerenciamento:

- **System Center Operations Manager** Com esse método, você usa o Operations Manager para adicionar o monitoramento para o Skype for Business Server.

- **Shell do Operations Manager** Você pode usar o Shell do Operations Manager para importar diretamente ou solucionar problemas encontrados ao importar pacotes de gerenciamento usando o console do System Center Operations Manager.

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>Importando os pacotes de gerenciamento usando o System Center Operations Manager

1. Baixe o SkypeForBusiness2019ManagementPacks. msi dos downloads da Microsoft na Web e instale o MSI.

2. No System Center Operations Manager, clique em **Administração**.

3. No painel Administração, clique com o botão direito do mouse em **Pacotes de gerenciamento** e, em seguida, clique em **Importar pacotes de gerenciamento**.

4. Na caixa de diálogo **Selecinar pacotes de gerenciamento**, clique em **Adicionar** e, em seguida, em **Adicionar do disco**.

5. Na caixa de diálogo **conexão do catálogo online** , clique em **não**.

6. Na caixa de diálogo **selecionar pacotes de gerenciamento a serem importados** , localize e selecione os arquivos Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp e Microsoft.ls.2019.Monitoring.ComponentAndUser.MP e clique em **abrir**. Para selecionar vários arquivos na caixa de diálogo, clique no primeiro arquivo e, em seguida, pressione a tecla CTRL e clique nos arquivos subsequentes.

7. Na caixa de seleção **Selecionar pacotes de gerenciamento**, clique em **Instalar**. Se receber uma mensagem de erro e a instalação falhar, geralmente isso signfica que os arquivos dos pacotes de gerenciamento estão em uma pasta protegida pelo Controle de conta de usuário do Windows. Se isso ocorrer, copie os arquivos para uma pasta diferente e reinicie o processo de importação e instalação.

8. Na caixa de diálogo **Selecionar pacotes de gerenciamento**, clique em **Fechar**. O processo de importação e instalação pode exigir vários minutos para ser concluído.

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a>Importando os pacotes de gerenciamento usando o Shell do Operations Manager

Em geral, é mais fácil importar os pacotes de gerenciamento usando o console do Operations Manager. No entanto, se ocorrer um erro e a importação falhar, o console nem sempre fornecerá os relatórios de erro adequados. Por comparação, o Shell do Operations Manager fornece informações detalhadas. Se você estiver usando o Operations Manager e encontrar problemas ao importar um pacote de gerenciamento, importe o pacote usando o Shell do Operations Manager. As informações fornecidas pelo shell do Operations Manager podem ajudá-lo a determinar o motivo da falha da importação.

1. Clique **em Iniciar**, **em todos os programas**, em **Microsoft System Center 2012**, em **Operations Manager**e em **shell do Operations Manager**.

2. No Shell do Operations Manager, digite o seguinte comando no prompt de comando, usando o caminho real para a sua cópia do arquivo Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp e pressione ENTER:

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp"
   ```

3. Depois de importar o primeiro pacote de gerenciamento, repita o processo usando o caminho até sua cópia do arquivo Microsoft.LS.2019.Monitoring.ComponentAndUser.mp:

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ComponentAndUser.mp"
   ```
