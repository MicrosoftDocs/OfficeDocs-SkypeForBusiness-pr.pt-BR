---
title: Configurar o Servidor de Gerenciamento Primário
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 872459f99f2e620d3d34db1196a8618476650c98
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806061"
---
# <a name="configure-the-primary-management-server"></a>Configurar o Servidor de Gerenciamento Primário

**Resumo:** Configure seu servidor de gerenciamento principal, instale o System Center Operations Manager e importe pacotes de gerenciamento para o Skype for Business Server 2019.

Para aproveitar ao máximo os novos recursos de monitoramento de saúde incluídos no Skype for Business Server 2019, primeiro você deve designar um computador para atuar como seu servidor de gerenciamento principal. Em seguida, você deve instalar o System Center Operations Manager 2012 SP1 ou R2 ou o System Center Operations Manager 2007 R2 nesse computador. Além disso, você deve instalar primeiro uma versão suportada do SQL Server para funcionar como seu banco de dados back-end do Operations Manager.

Ao instalar o System Center Operations Manager, você precisará instalar todos os componentes desse produto, incluindo:

- Banco de dados operacional

- Servidor

- Console

- \s-1 \plain Windows PowerShellcmdlets

- Console da Web

- Relatório

- Data warehouse

> [!IMPORTANT]
> O "[Microsoft Report Viewer 2010 Redistributable Package](https://www.microsoft.com/download/details.aspx?id=6442)" precisa ser instalado antes de instalar o System Center Operations Manager 2012.

Para obter detalhes sobre esses produtos e sua instalação, consulte os seguintes links:

- [System Center Operations Manager 2012](https://go.microsoft.com/fwlink/p/?linkid=257527)

- [System Center Operations Manager 2007](https://technet.microsoft.com/library/bb735860.aspx)

Tenha em mente que você pode ter apenas um Servidor de Gerenciamento Raiz por implantação do Skype for Business Server.

## <a name="importing-the-skype-for-business-server-2019-management-packs"></a>Importando os Pacotes de Gerenciamento do Skype for Business Server 2019

Você pode estender os recursos do System Center Operations Manager instalando pacotes de gerenciamento — software que determina quais itens o System Center Operations Manager pode monitorar, como esses itens devem ser monitorados e como os alertas devem ser disparados e relatados. O Skype for Business Server 2019 inclui dois pacotes de gerenciamento do System Center Operations Manager que fornecem os seguintes recursos:

- O **Pacote** de Gerenciamento de Componente e Usuário (Microsoft.LS.2019.Monitoring.ComponentAndUser.mp) rastreia problemas do Skype for Business Server registrados em logs de eventos, registrados por contadores de desempenho ou registrados nos cdRs (registros de detalhes das chamadas) ou nos bancos de dados de QoE (Qualidade da Experiência). Para problemas críticos, o System Center Operations Manager pode ser configurado para notificar os administradores imediatamente por email, mensagem instantânea ou sms. (SMS ou Serviço de Mensagens Curtas é a tecnologia usada para enviar mensagens de texto de um dispositivo móvel para outro.)

    > [!NOTE]
    >  Para obter detalhes sobre como configurar a notificação do Operations Manager, consulte [Configuring Notification](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409).

- O **Active Monitoring Management Pack** (Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp) testa proativamente os principais componentes do Skype for Business Server, como entrar no sistema, trocar mensagens instantâneas ou fazer chamadas para um telefone localizado na PSTN (rede telefônica pública comuada). Esses testes são realizados usando os cmdlets de transação sintética do Skype for Business Server. Por exemplo, o cmdlet **Test-CsIM** é usado para simular uma conversa de mensagem instantânea entre um par de usuários de teste. Se essa conversa simulada falhar, um alerta será gerado.

Importar os pacotes de gerenciamento é uma etapa crucial. Se os pacotes de gerenciamento não são importados, você não poderá usar o Operations Manager para monitorar eventos do Skype for Business Server ou executar transações sintéticas do Skype for Business Server.

O Pacote de Gerenciamento de Componentes e Usuários é usado para monitorar apenas o Skype for Business Server 2019. Se você estiver em um cenário de coexistência em que tanto o Skype for Business Server 2019 quanto o Skype for Business Server 2015 estão instalados, você deve continuar a usar os pacotes de gerenciamento do Skype for Business Server 2015 para seus computadores do Skype for Business Server 2015.

> [!NOTE]
> Os pacotes de gerenciamento do Skype for Business Server 2019 incluem o Pacote de Gerenciamento de Componentes e Usuários do Skype for Business Server 2019 e o Pacote de Gerenciamento de Monitoramento Ativo do Skype for Business Server 2019.

Você pode usar uma destas ferramentas para importar pacotes de gerenciamento:

- **System Center Operations Manager** Com esse método, você usa o Operations Manager para adicionar monitoramento para o Skype for Business Server.

- **Shell do Operations Manager** Você pode usar o Shell do Operations Manager para importar diretamente ou solucionar quaisquer problemas encontrados ao importar pacotes de gerenciamento usando o console do System Center Operations Manager.

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>Importando os pacotes de gerenciamento usando o System Center Operations Manager

1. Baixe a SkypeForBusiness2019ManagementPacks.msi dos downloads da Microsoft Web e instale o msi.

2. No System Center Operations Manager, clique em **Administração.**

3. No painel Administração, clique com o botão direito do mouse em **Pacotes de gerenciamento** e, em seguida, clique em **Importar pacotes de gerenciamento**.

4. Na caixa de diálogo **Selecinar pacotes de gerenciamento**, clique em **Adicionar** e, em seguida, em **Adicionar do disco**.

5. Na caixa **de diálogo Conexão do Catálogo Online,** clique em **Não**.

6. Na caixa **de diálogo** Selecionar Pacotes de Gerenciamento para importar, localize e selecione os arquivos Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp e Microsoft.LS.2019.Monitoring.ComponentAndUser.mp e clique em **Abrir.** Para selecionar vários arquivos na caixa de diálogo, clique no primeiro arquivo, mantenha a tecla Ctrl e clique nos arquivos subsequentes.

7. Na caixa de seleção **Selecionar pacotes de gerenciamento**, clique em **Instalar**. Se receber uma mensagem de erro e a instalação falhar, geralmente isso signfica que os arquivos dos pacotes de gerenciamento estão em uma pasta protegida pelo Controle de conta de usuário do Windows. Se isso ocorrer, copie os arquivos para uma pasta diferente e reinicie o processo de importação e instalação.

8. Na caixa de diálogo **Selecionar pacotes de gerenciamento**, clique em **Fechar**. O processo de importação e instalação pode exigir vários minutos para ser concluído.

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a>Importando os pacotes de gerenciamento usando o Shell do Operations Manager

Em geral, é mais fácil importar os pacotes de gerenciamento usando o console do Operations Manager. No entanto, se ocorrer um erro e a importação falhar, o console nem sempre fornecerá relatórios de erro adequados. Em comparação, o Shell do Operations Manager fornece informações detalhadas. Se você estiver usando o Operations Manager e tiver problemas ao importar um pacote de gerenciamento, importe o pacote usando o Shell do Operations Manager. As informações fornecidas pelo Shell do Operations Manager podem ajudá-lo a determinar por que a importação falhou.

1. Clique **em** Iniciar, em **Todos os Programas,** em **Microsoft System Center 2012,** em **Operations Manager** e em Shell do **Operations Manager.**

2. No Shell do Operations Manager, digite o seguinte comando no prompt de comando, usando o caminho real para sua cópia do arquivo Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp e pressione ENTER:

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp"
   ```

3. Depois de importar o primeiro pacote de gerenciamento, repita o processo, usando o caminho para sua cópia do arquivo Microsoft.LS.2019.Monitoring.ComponentAndUser.mp:

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ComponentAndUser.mp"
   ```
