---
title: Configurar o Servidor de Gerenciamento principal
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumo: Configurar o servidor de gerenciamento primário, instalar o System Center Operations Manager e importar pacotes de gerenciamento para Skype para Business Server 2019.'
ms.openlocfilehash: 39ed469227c607084dc030fa003700074a6aae9a
ms.sourcegitcommit: 139b3d3b7fcc1dd7fba7fd14ff34e4ffdfcc7eeb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2018
ms.locfileid: "26216081"
---
# <a name="configure-the-primary-management-server"></a>Configurar o Servidor de Gerenciamento principal

**Resumo:** Configurar o servidor de gerenciamento primário, instalar o System Center Operations Manager e importar pacotes de gerenciamento para Skype para Business Server 2019.

Para aproveitar totalmente a nova recursos incluídos no Skype para Business Server 2019 de monitoramento de integridade, você deve primeiro designar um computador para atuar como seu servidor de gerenciamento primário. Em seguida, você deve instalar o System Center Operations Manager 2012 SP1 ou R2 ou o System Center Operations Manager 2007 R2 no computador. Além disso, primeiro instale uma versão compatível do SQL Server para funcionar como seu banco de dados de back-end do Operations Manager.

Quando você instala o System Center Operations Manager, você precisará instalar todos os componentes de tal produto, incluindo:

- Banco de dados operacional

- Servidor

- Console

- Cmdlets do Windows PowerShell

- Console da Web

- Relatório

- Data warehouse

> [!IMPORTANT]
> O "[Pacote redistribuível do Microsoft relatório Viewer 2010](https://www.microsoft.com/en-us/download/details.aspx?id=6442)" precisa ser instalado antes de instalar o System Center Operations Manager 2012.

Para obter detalhes sobre esses produtos e sua instalação, consulte os seguintes links:

- [System Center Operations Manager 2012](https://go.microsoft.com/fwlink/p/?linkid=257527)

- [System Center Operations Manager 2007](https://technet.microsoft.com/en-us/library/bb735860.aspx)

Tenha em mente que você pode ter apenas um servidor de gerenciamento raiz por Skype para implantação de servidor de negócios.

## <a name="importing-the-skype-for-business-server-2019-management-packs"></a>Importando o Skype para pacotes de gerenciamento do Business Server 2019

Você pode estender os recursos do System Center Operations Manager por meio da instalação de pacotes de gerenciamento — software que exigida pela qual os itens do System Center Operations Manager pode monitorar, como os itens devem ser monitorados e como alertas devem ser disparadas e relatado. Skype para Business Server 2019 inclui dois pacotes de gerenciamento do System Center Operations Manager que fornecem os seguintes recursos:

- **O componente e o pacote de gerenciamento do usuário** (Microsoft.LS.2019.Monitoring.ComponentAndUser.mp) rastreia Skype para problemas do Business Server registrada nos logs de eventos, registrados por contadores de desempenho ou logado os registros de detalhes de chamadas (CDRs) ou os bancos de dados de qualidade da experiência (QoE). Para resolver problemas críticos o System Center Operations Manager pode ser configurado para notificar imediatamente os administradores por meio de email, mensagem instantânea ou mensagens de SMS. (SMS é a tecnologia usada para o envio de mensagens de texto de um dispositivo móvel para outro.)

    > [!NOTE]
    >  Para obter detalhes sobre como configurar a notificação do Operations Manager, consulte [Configurando a notificação](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409).

- **O pacote de gerenciamento de monitoramento ativo** (Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp) proativamente testes principais Skype para componentes de servidor de negócios, fazer o login no sistema, trocando mensagens instantâneas ou fazer chamadas para um telefone localizado na PSTN (rede telefônica pública comutada ). Esses testes são realizados com o uso de cmdlets de transação sintéticos do Skype for Business Server. Por exemplo, o cmdlet **Test-CsIM** é usado para simular uma conversa de mensagens instantâneas entre um par de usuários de teste. Se essa conversa simulada falhar, um alerta será gerado.

A importação dos pacotes de gerenciamento é uma etapa crucial. Se os pacotes de gerenciamento não forem importados, você não poderá usar o Operations Manager para monitorar eventos do Skype for Business Server ou executar transações sintéticas do Skype for Business Server.

O componente e o pacote de gerenciamento do usuário é usado para monitorar somente Skype Business Server 2019. Se você estiver em um cenário de coexistência onde Skype para Business Server 2019 e o Skype para Business Server 2015 estão instalados, você deve continuar a usar o Skype para pacotes de gerenciamento de negócios Server 2015 para seu Skype para computadores Business Server 2015.

> [!NOTE]
> Pacotes de gerenciamento do Skype para Business Server 2019 incluem o Skype para Business Server 2019 componente e o pacote de gerenciamento do usuário e o Skype para Business Server 2019 ativo Monitoring Management Pack.

Você pode usar uma destas ferramentas para importar pacotes de gerenciamento:

- **System Center Operations Manager** Com este método, você pode usar o Operations Manager para adicionar o monitoramento para Skype para Business Server.

- **Shell do Operations Manager** Você pode usar o Shell do Operations Manager para importar diretamente ou solucionar quaisquer problemas que você encontrar ao importar pacotes de gerenciamento usando o console do System Center Operations Manager.

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>Importando os pacotes de gerenciamento usando o System Center Operations Manager

1. Baixe o SkypeForBusiness2019ManagementPacks.msi dos downloads do Microsoft Web e instalar o msi.

2. No System Center Operations Manager, clique em **Administração**.

3. No painel administração, do mouse em **Pacotes de gerenciamento**e, em seguida, clique em **Importar pacotes de gerenciamento**.

4. Na caixa de diálogo **Selecionar Pacotes de Gerenciamento**, clique em **Adicionar** e, em seguida, em **Adicionar do disco**.

5. Na caixa de diálogo **Conexão do Catálogo Online**, clique em **Não**.

6. Na caixa de diálogo **Selecionar pacotes de gerenciamento para importar** , localize e selecione os arquivos Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp e Microsoft.LS.2019.Monitoring.ComponentAndUser.mp e, em seguida, clique em **Abrir**. Para selecionar vários arquivos na caixa de diálogo, clique no primeiro arquivo, mantenha pressionada a tecla Ctrl e clique nos arquivos subsequentes.

7. Na caixa de seleção **Selecionar pacotes de gerenciamento**, clique em **Instalar**. Se receber uma mensagem de erro e a instalação falhar, geralmente isso significa que os arquivos dos pacotes de gerenciamento estão em uma pasta protegida pelo Controle de conta de usuário do Windows. Se isso ocorrer, copie os arquivos para outra pasta e reinicie o processo de instalação e importação.

8. Na caixa de diálogo **Selecionar pacotes de gerenciamento**, clique em **Fechar**. A conclusão do processo de importação e instalação pode levar muitos minutos.

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a>Importando os pacotes de gerenciamento usando o Shell do Operations Manager

Em geral, é mais fácil importar os pacotes de gerenciamento usando o console do Operations Manager. No entanto, se ocorrer um erro e a importação falhar, o console nem sempre fornecerá relatórios de erro adequados. Em comparação, o Shell do Operations Manager fornece informações detalhadas. Se você estiver usando o Operations Manager e tiver problemas ao importar um pacote de gerenciamento, importe o pacote usando o Shell do Operations Manager. As informações fornecidas pelo Shell do Operations Manager podem ajudá-lo a determinar por que a importação falhou.

1. Clique em **Iniciar**, **Todos os Programas**, **Microsoft System Center 2012**, **Operations Manager** e **Shell do Operations Manager**.

2. No Shell do Operations Manager, digite o seguinte comando no prompt de comando, usando o caminho até sua cópia do arquivo Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp e pressione ENTER:

   ```
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp"
   ```

3. Depois de ter importado o primeiro pacote de gerenciamento, repita o processo, usando o caminho até sua cópia do arquivo Microsoft.LS.2019.Monitoring.ComponentAndUser.mp:

   ```
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ComponentAndUser.mp"
   ```