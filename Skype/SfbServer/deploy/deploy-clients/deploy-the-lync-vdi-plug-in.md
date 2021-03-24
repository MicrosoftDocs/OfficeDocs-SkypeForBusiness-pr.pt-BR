---
title: Implantar o plug-in VDI do Lync com o Skype for Business Server
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: krishra
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: Este tópico discute procedimentos de implantação para usar o Skype for Business ao se conectar a uma área de trabalho virtual remota.
ms.openlocfilehash: 6db05fb3bcd9638a3181eb454de3a3097831b997
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095995"
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server"></a>Implantar o plug-in VDI do Lync com o Skype for Business Server
 
Este tópico discute procedimentos de implantação para usar o Skype for Business ao se conectar a uma área de trabalho virtual remota. As considerações de planejamento estão [em Plan for Skype for Business em ambientes VDI.](../../plan-your-deployment/clients-and-devices/vdi-environments.md)
  
Um Virtual Desktop Infrastructure (VDI) é usado em algumas organizações onde os problemas de segurança e conformidade são especialmente confidenciais. Seus usuários estão em computadores Locais do Windows e usando clientes em uma área de trabalho virtual. Usar o Skype for Business em uma conexão como essa requer software de plug-in VDI adicional.
  
Há duas soluções disponíveis para o componente de plug-in VDI : uma oferecida pela Microsoft e outra oferecida pela Citrix. A Microsoft recomenda usar a nova solução HDX RealTime Optimization Pack em novas implantações, mas continuará a dar suporte ao Plug-in VDI original do Lync para o restante do ciclo de vida. 
  
Este tópico fornece detalhes sobre como implantar o plug-in VDI do Microsoft Lync, que só é compatível com o Windows 7 e o Windows 8 ou o Windows Server 2008, e dá suporte apenas a clientes do Lync 2013 ou skype for Business. Não há planos para atualizar esse plug-in, mas o [Citrix HDX RealTime Optimization Pack](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) for Skype for Business será atualizado conforme necessário.
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a>Preparar seu ambiente para o plug-in VDI do Lync
<a name="Prepare_vdi"> </a>

1. No Skype for Business Server, verifique se EnableMediaRedirection está definido como VERDADEIRO para todos os usuários de plug-in VDI do Lync. Para obter detalhes, consulte os tópicos de Ajuda para o cmdlet [New-CsClientPolicy](/powershell/module/skype/new-csclientpolicy?view=skype-ps) e o cmdlet [Set-CsClientPolicy.](/powershell/module/skype/set-csclientpolicy?view=skype-ps)
    
2. No servidor do data center, instale o cliente skype for Business em todas as áreas de trabalho virtuais.
    
3. Nos computadores locais, instale o plug-in VDI do Lync.
    
    Os usuários agora devem conectar um dispositivo como um fone de ouvido ou webcam ao computador local.
    
## <a name="configure-remote-desktop-connection-settings"></a>Configurar configurações de Conexão de Área de Trabalho Remota
<a name="Prepare_vdi"> </a>

Para preparar a Conexão de Área de Trabalho Remota para o plug-in VDI do Lync, siga estas etapas no computador local:
  
1. Se o computador local estiver executando o Windows 8, ignore esta etapa. Se o computador local estiver executando o Windows 7 com SP1, instale a versão mais recente do Windows 8 do cliente de Serviços de [Área de Trabalho Remota](/windows-server/remote/remote-desktop-services/clients/remote-desktop-clients).
    
2. Inicie o cliente dos Serviços de Área de Trabalho Remota clicando em **Iniciar** e em **Conexão da Área de Trabalho Remota**.
    
3. Clique em **Opções**.
    
4. Clique na guia **Recursos locais**. Em **Áudio remoto**, clique em **Configurações** e faça o seguinte:
    
   - Em **Reprodução de áudio remoto**, selecione **Reproduzir neste computador**.
    
   - Em **Gravação de áudio remoto**, selecione **Não gravar**.
    
   - Clique em **OK**.
    
5. Clique na guia **Experiência**. Em **Desempenho**, desmarque a caixa de seleção **Cache de bitmap persistente**.
    
6. Clique na **guia Geral.** Em **Computador**, digite o nome da área de trabalho virtual e clique em **Conectar**. 
    
## <a name="sign-in-and-use-skype-for-business-on-the-virtual-desktop"></a>Entre e use o Skype for Business na área de trabalho virtual
<a name="SfB_signin"> </a>

Depois que o plug-in VDI do Lync estiver habilitado, o usuário seguirá estas etapas ao entrar no Skype for Business na área de trabalho virtual.
  
1. O usuário digita suas credenciais para o cliente skype for Business em execução na área de trabalho virtual.
    
2. Depois que o Skype for Business detecta o plug-in VDI do Lync, o Skype for Business solicita que o usuário insira as credenciais. Nessa caixa de diálogo, é recomendável que o usuário marque a caixa de seleção **Salvar minha senha** para que não precise inserir as credenciais na próxima entrada.
    
3. O Skype for Business começa a emparelhar com o plug-in VDI do Lync. Enquanto isso acontece, o cliente exibe dois ícones na barra de status do Skype for Business. O ícone na parte inferior esquerda indica que nenhum dispositivo de áudio está disponível, e o ícone piscando no canto inferior direito indica que o emparelhamento VDI está em andamento: a. Depois que o emparelhamento VDI for bem-sucedido, os ícones mudarão para indicar o dispositivo de áudio que será usado para chamadas e o sucesso de emparelhamento VDI: b. Agora, o usuário pode ver sua presença em dispositivos compatíveis com o Skype for Business que estão conectados ao computador local e fazer e atender chamadas, como de costume.
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a>Solucionar problemas do plug-in VDI do Lync
<a name="tshoot_VDI"> </a>

Consulte as seções a seguir se você encontrar problemas depois de instalar o plug-in VDI do Lync.
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a>Problemas com a instalação do Plug-in VDI do Lync

Se houver problemas com a instalação do plug-in VDI do Lync, verifique o seguinte:
  
- Assegure-se de que há espaço em disco suficiente na pasta que você especificou nas variáveis do sistema TEMP e TMP.
    
- Assegure-se de que a proteção contra gravação está desligada. Consulte a documentação do fabricante do dispositivo para obter instruções.
    
### <a name="troubleshooting-issues-with-pairing"></a>Solucionando problemas com pareamento

Quando o emparelhamento de plug-in VDI do Lync falha, o ícone de emparelhamento no canto inferior direito é exibido como um "X" vermelho, conforme mostrado: 
  
A seguir estão os possíveis motivos para falhas e as ações que você pode realizar para corrigir o problema. 
  
- **O usuário inseriu credenciais incorretas durante a entrada.**
    
    O usuário deve sair do Skype for Business e entrar novamente com as credenciais corretas. A caixa de diálogo de pareamento reaparecerá e mostrará se o pareamento teve êxito.
    
- **Outra instância do cliente de área de trabalho remota está sendo executada.**
    
    Se eles estão usando a Conexão de Área de Trabalho Remota no Windows, os usuários devem fazer o seguinte:
    
1. Iniciar o Gerenciador de Tarefas: pressionar **Alt+Ctrl+Delete**, e então clicar em **Iniciar Gerenciador de Tarefas**.
    
2. Clique na guia **Processos** e procure por todos os processos chamados **mstsc.exe** na lista.
    
3. Selecione cada processo **mstsc.exe** e então clique em **Finalizar Processo**. 
    
4. Inicie uma nova sessão de área de trabalho remota e tente conectar novamente. 
    
- **Os arquivos necessários não foram instalados corretamente.**
    
    Depois que o plug-in for instalado no computador local, verifique se esses arquivos estão presentes em C:\Program Files\Microsoft Office\Office15 (ou a letra da unidade apropriada):
    
  - LyncVdiPlugin.dll
    
  - UcVdi.dll
    
- **O cliente skype for Business está sendo executado no computador local.**
    
    Para usar o plug-in VDI do Lync, um cliente do Skype for Business não deve estar em execução no computador local, caso contrário, o emparelhamento falhará. Como prática prática, o usuário não deve instalar um cliente do Skype for Business no computador local.
    
## <a name="see-also"></a>Confira também
<a name="tshoot_VDI"> </a>

[Planejar o Skype for Business em ambientes VDI](../../plan-your-deployment/clients-and-devices/vdi-environments.md)