---
title: Configurar o Servidor de Gerenciamento principal
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumo: configure seu servidor de gerenciamento primário, instale o System Center Operations Manager e importe pacotes de gerenciamento para o Skype for Business Server 2019.'
ms.openlocfilehash: 316931aff5379de10b0301cc65e94443ed0f7675
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284036"
---
# <a name="configure-the-primary-management-server"></a>Configurar o Servidor de Gerenciamento principal

**Resumo:** Configure seu servidor de gerenciamento primário, instale o System Center Operations Manager e importe pacotes de gerenciamento para o Skype for Business Server 2019.

Para aproveitar ao máximo os novos recursos de monitoramento de integridade incluídos no Skype for Business Server 2019, você deve primeiro designar um computador para atuar como seu servidor de gerenciamento principal. Você deve instalar o System Center Operations Manager 2012 SP1 ou R2 ou o System Center Operations Manager 2007 R2 nesse computador. Além disso, você deve primeiro instalar uma versão com suporte do SQL Server para funcionar como o banco de dados back-end do Operations Manager.

Ao instalar o System Center Operations Manager, você precisará instalar todos os componentes desse produto, incluindo:

- Banco de dados operacional

- Servidor

- Console

- Cmdlets do Windows PowerShell

- Console da Web

- Relatório

- Data warehouse

> [!IMPORTANT]
> O "[pacote redistribuível do Microsoft Report Viewer 2010](https://www.microsoft.com/en-us/download/details.aspx?id=6442)" precisa ser instalado antes de instalar o System Center Operations Manager 2012.

Para obter detalhes sobre esses produtos e sua instalação, consulte os seguintes links:

- [System Center Operations Manager 2012](https://go.microsoft.com/fwlink/p/?linkid=257527)

- [System Center Operations Manager 2007](https://technet.microsoft.com/en-us/library/bb735860.aspx)

Lembre-se de que você só pode ter um servidor de gerenciamento raiz por implantação do Skype for Business Server.

## <a name="importing-the-skype-for-business-server-2019-management-packs"></a>Importando os pacotes de gerenciamento do Skype for Business Server 2019

Você pode estender os recursos do System Center Operations Manager Instalando pacotes de gerenciamento — software que determina quais itens o System Center Operations Manager pode monitorar, como esses itens devem ser monitorados e como os alertas devem ser acionados e menciona. O Skype for Business Server 2019 inclui dois pacotes de gerenciamento do System Center Operations Manager que fornecem os seguintes recursos:

- **O pacote de gerenciamento de componentes e usuários** (Microsoft.LS.2019.Monitoring.ComponentAndUser.mp) controla os problemas do Skype for Business Server registrados nos logs de eventos, registrados pelos contadores de desempenho, ou registrados nos bancos de dados de registros de detalhes de chamadas (CDRs) ou de qualidade da experiência (QoE). Para problemas críticos, o System Center Operations Manager pode ser configurado para notificar imediatamente os administradores por email, mensagem instantânea ou mensagens SMS. (SMS é a tecnologia usada para o envio de mensagens de texto de um dispositivo móvel para outro.)

    > [!NOTE]
    >  Para obter detalhes sobre como configurar a notificação do Operations Manager, consulte Configurando a [notificação](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409).

- **O pacote de gerenciamento de monitoramento ativo** (Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp) testa proativamente os principais componentes do Skype for Business Server, como entrar no sistema, trocar mensagens de chat ou fazer chamadas para um telefone localizado na rede telefônica pública comutada (PSTN). ). Esses testes são realizados com o uso de cmdlets de transação sintéticos do Skype for Business Server. Por exemplo, o cmdlet **Test-CsIM** é usado para simular uma conversa de mensagens instantâneas entre um par de usuários de teste. Se essa conversa simulada falhar, um alerta será gerado.

A importação dos pacotes de gerenciamento é uma etapa crucial. Se os pacotes de gerenciamento não forem importados, você não poderá usar o Operations Manager para monitorar eventos do Skype for Business Server ou executar transações sintéticas do Skype for Business Server.

O pacote de gerenciamento de componentes e usuários é usado para monitorar somente o Skype for Business Server 2019. Se você estiver em um cenário de coexistência onde o Skype for Business Server 2019 e o Skype for Business Server 2015 estiverem instalados, você deve continuar a usar os pacotes de gerenciamento do Skype for Business Server 2015 para seus computadores com o Skype for Business Server 2015.

> [!NOTE]
> Os pacotes de gerenciamento do Skype for Business Server 2019 incluem o componente do Skype for Business Server 2019 e o pacote de gerenciamento do usuário e o pacote de gerenciamento ativo do Skype for Business Server 2019.

Você pode usar uma destas ferramentas para importar pacotes de gerenciamento:

- **Gerenciador de operações do System Center** Com esse método, você usa o Operations Manager para adicionar monitoramento para o Skype for Business Server.

- **Shell do Operations Manager** Você pode usar o Shell do Operations Manager para importar diretamente ou solucionar problemas que você encontra quando importa pacotes de gerenciamento usando o console do System Center Operations Manager.

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>Importando os pacotes de gerenciamento usando o System Center Operations Manager

1. Baixe o SkypeForBusiness2019ManagementPacks. msi do download da Microsoft na Web e instale o MSI.

2. No System Center Operations Manager, clique em **Administração**.

3. No painel Administração, clique com o botão direito do mouse em **pacotes de gerenciamento**e, em seguida, clique em **importar pacotes de gerenciamento**.

4. Na caixa de diálogo **Selecionar Pacotes de Gerenciamento**, clique em **Adicionar** e, em seguida, em **Adicionar do disco**.

5. Na caixa de diálogo **Conexão do Catálogo Online**, clique em **Não**.

6. Na caixa de diálogo **selecionar pacotes de gerenciamento a serem** importados, localize e selecione os arquivos Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp e Microsoft.ls.2019.Monitoring.ComponentAndUser.MP e, em seguida, clique em **abrir**. Para selecionar vários arquivos na caixa de diálogo, clique no primeiro arquivo e, em seguida, mantenha pressionada a tecla CTRL e clique nos arquivos subsequentes.

7. Na caixa de seleção **Selecionar pacotes de gerenciamento**, clique em **Instalar**. Se receber uma mensagem de erro e a instalação falhar, geralmente isso significa que os arquivos dos pacotes de gerenciamento estão em uma pasta protegida pelo Controle de conta de usuário do Windows. Se isso ocorrer, copie os arquivos para outra pasta e reinicie o processo de instalação e importação.

8. Na caixa de diálogo **Selecionar pacotes de gerenciamento**, clique em **Fechar**. A conclusão do processo de importação e instalação pode levar muitos minutos.

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a>Importando os pacotes de gerenciamento usando o Shell do Operations Manager

Em geral, é mais fácil importar os pacotes de gerenciamento usando o console do Operations Manager. No entanto, se ocorrer um erro e a importação falhar, o console nem sempre fornecerá relatórios de erro adequados. Em comparação, o Shell do Operations Manager fornece informações detalhadas. Se você estiver usando o Operations Manager e tiver problemas ao importar um pacote de gerenciamento, importe o pacote usando o Shell do Operations Manager. As informações fornecidas pelo Shell do Operations Manager podem ajudá-lo a determinar por que a importação falhou.

1. Clique em **Iniciar**, **Todos os Programas**, **Microsoft System Center 2012**, **Operations Manager** e **Shell do Operations Manager**.

2. No Shell do Operations Manager, digite o seguinte comando no prompt de comando, usando o caminho real para a sua cópia do arquivo Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp e, em seguida, pressione ENTER:

   ```
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp"
   ```

3. Depois de importar o primeiro pacote de gerenciamento, repita o processo usando o caminho para a sua cópia do arquivo Microsoft.LS.2019.Monitoring.ComponentAndUser.mp:

   ```
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ComponentAndUser.mp"
   ```
