---
title: Implantar o plug-in VDI do Lync com o Skype for Business Server
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: krishra
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: Este tópico discute os procedimentos de implantação para usar o Skype for Business enquanto se conecta a uma área de trabalho virtual remota.
ms.openlocfilehash: f864136ab55f37a9bfaf54d6c31d74d31844da59
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768940"
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server"></a>Implantar o plug-in VDI do Lync com o Skype for Business Server
 
Este tópico discute os procedimentos de implantação para usar o Skype for Business enquanto se conecta a uma área de trabalho virtual remota. As considerações de planejamento estão no [plano para o Skype for Business em ambientes VDI](../../plan-your-deployment/clients-and-devices/vdi-environments.md).
  
Um ambiente VDI (Virtual Desktop Infrastructure) é usado em algumas organizações nas quais questões de segurança e conformidade são especialmente sensíveis. Seus usuários trabalham em computadores Windows locais e utilizam clientes em uma área de trabalho virtual. Usar o Skype for Business em uma conexão como essa requer software de plug-in VDI adicional.
  
Há duas soluções disponíveis para o componente plug-in VDI – uma oferecida pela Microsoft e uma oferecida pela Citrix. A Microsoft recomenda o uso da nova solução de pacote de otimização HDX RealTime em novas implantações, mas continuará a oferecer suporte ao plug-in do VDI do Lync original para o restante do ciclo de vida. 
  
Este tópico fornece detalhes sobre a implantação do plug-in VDI do Microsoft Lync, que só tem suporte no Windows 7 e Windows 8 ou no Windows Server 2008, e só tem suporte para os clientes do Lync 2013 ou do Skype for Business. Não há planos para atualizar este plugin, mas o [pacote de otimização do Citrix HDX Realtime](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) para o Skype for Business será atualizado conforme necessário.
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a>Preparar seu ambiente para o plug-in VDI do Lync
<a name="Prepare_vdi"> </a>

1. No Skype for Business Server, certifique-se de que o EnableMediaRedirection está definido como TRUE para todos os usuários de plug-in do Lync da VDI. Para obter detalhes, consulte os tópicos da ajuda para o cmdlet [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) e o cmdlet [set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) .
    
2. No servidor do Data Center, instale o cliente Skype for Business em todas as áreas de trabalho virtuais.
    
3. Nos computadores locais, instale o plug-in VDI do Lync.
    
    Os usuários agora devem conectar um dispositivo, como um fone de ouvido com microfone ou uma webcam, ao computador local.
    
## <a name="configure-remote-desktop-connection-settings"></a>Definir as configurações da Conexão de Área de Trabalho Remota
<a name="Prepare_vdi"> </a>

Para preparar a conexão de área de trabalho remota para o plug-in VDI do Lync, siga estas etapas no computador local:
  
1. Se o computador local estiver executando o Windows 8, pule esta etapa. Se o computador local estiver executando o Windows 7 com SP1, instale a versão mais recente do Windows 8 do [cliente dos serviços de área de trabalho remota](https://go.microsoft.com/fwlink/p/?LinkId=268032).
    
2. Inicie o cliente de Serviços de Área de Trabalho Remota clicando em **Iniciar** e em **Conexão de Área de Trabalho Remota**.
    
3. Clique em **Opções**.
    
4. Clique na guia **Recursos Locais**. Em **Áudio remoto**, clique em **Configurações** e faça o seguinte:
    
   - Em **Reprodução de áudio remoto**, selecione **Reproduzir neste computador**.
    
   - Em **Gravação de áudio remoto**, selecione **Não gravar**.
    
   - Clique em **OK**.
    
5. Clique na guia **Experiência**. Em **Desempenho**, desmarque a caixa de seleção **Armazenamento persistente de bitmaps em cache**.
    
6. Clique na guia **Geral**. Em **Computador**, digite o nome da área de trabalho virtual e clique em **Conectar**.  
    
## <a name="sign-in-and-use-skype-for-business-on-the-virtual-desktop"></a>Entrar e usar o Skype for Business na área de trabalho virtual
<a name="SfB_signin"> </a>

Depois que o plug-in VDI do Lync estiver habilitado, o usuário seguirá estas etapas ao entrar no Skype for Business na área de trabalho virtual.
  
1. O usuário digita suas credenciais para o cliente Skype for Business em execução na área de trabalho virtual.
    
2. Depois que o Skype for Business detectar o plug-in VDI do Lync, o Skype for Business solicitará que o usuário digite novamente as credenciais. Nessa caixa de diálogo, é recomendável que o usuário marque a caixa de seleção **Salvar minha senha** para que não precise inserir as credenciais na próxima entrada.
    
3. O Skype for Business começa a emparelhar com o plug-in VDI do Lync. Enquanto isso acontece, o cliente exibe dois ícones na barra de status do Skype for Business. O ícone no canto inferior esquerdo indica que não há dispositivos de áudio disponíveis, e o ícone piscante no canto inferior direito indica que o emparelhamento com VDI está em andamento: a. Após o emparelhamento com o VDI ter êxito, os ícones são alterados para indicar o dispositivo de áudio que será usado para chamadas e o sucesso de emparelhamento da VDI: b. Agora o usuário pode ver sua presença em dispositivos compatíveis com o Skype for Business que estão conectados ao computador local e fazer e atender chamadas normalmente.
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a>Solução de problemas do plug-in VDI do Lync
<a name="tshoot_VDI"> </a>

Consulte as seções a seguir se houver problemas após a instalação do plug-in Lync VDI.
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a>Problemas na instalação do plug-in VDI do Lync 

Se houver problemas para instalar o plug-in VDI do Lync, verifique o seguinte:
  
- Verifique se há espaço em disco suficiente na pasta que você especificou nas variáveis do sistema TEMP e TMP.
    
- Verifique se a proteção contra gravação está desativada. Consulte a documentação do fabricante do dispositivo para obter instruções.
    
### <a name="troubleshooting-issues-with-pairing"></a>Solução de problemas de emparelhamento

Quando o emparelhamento do plug-in do Lync da VDI falha, o ícone de emparelhamento no canto inferior direito é exibido como um "X" vermelho, conforme mostrado: 
  
Veja a seguir os possíveis motivos das falhas e as ações que você pode tomar para corrigir o problema.  
  
- **O usuário inseriu credenciais incorretas durante a entrada.**
    
    O usuário deve desconectar-se do Skype for Business e entrar novamente com as credenciais corretas. A caixa de diálogo de emparelhamento será exibida novamente e mostrará se o emparelhamento foi bem-sucedido.
    
- **Outra instância do cliente de área de trabalho remota está sendo executada.**
    
    Se eles estiverem usando a conexão de área de trabalho remota no Windows, os usuários devem fazer o seguinte:
    
1. Iniciar o Gerenciador de Tarefas: pressionar **Alt+Ctrl+Delete** e depois clicar em **Iniciar Gerenciador de Tarefas**.
    
2. Clicar na guia **Processos** e procurar todos os processos chamados **mstsc.exe** na lista.
    
3. Realçar cada processo **mstsc.exe** e clicar em **Finalizar Processo**.  
    
4. Iniciar uma nova sessão de área de trabalho remota e tentar conectar-se novamente.  
    
- **Os arquivos necessários não foram instalados corretamente.**
    
    Depois que o plug-in for instalado no computador local, verifique se estes arquivos estão presentes em C:\Arquivos de Programas\Microsoft Office\Office15 (ou na letra da unidade apropriada):
    
  - LyncVdiPlugin.dll
    
  - UcVdi.dll
    
- **O cliente Skype for Business está em execução no computador local.**
    
    Para usar o plug-in VDI do Lync, um cliente Skype for Business não deve estar em execução no computador local, caso contrário, haverá falha no emparelhamento. Como prática recomendada, o usuário não deve instalar um cliente Skype for Business no computador local.
    
## <a name="see-also"></a>Confira também
<a name="tshoot_VDI"> </a>

[Plan for Skype for Business in VDI environments](../../plan-your-deployment/clients-and-devices/vdi-environments.md)
