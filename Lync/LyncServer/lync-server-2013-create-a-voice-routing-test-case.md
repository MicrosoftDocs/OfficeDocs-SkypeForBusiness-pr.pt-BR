---
title: 'Lync Server 2013: criar um caso de teste de roteamento de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a voice routing test case
ms:assetid: 43a07a5b-2f20-462a-81e5-d628c18391e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425935(v=OCS.15)
ms:contentKeyID: 48183979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9fac6f65d1bb1c04b8d8597454df775f8545d2a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205747"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-voice-routing-test-case-in-lync-server-2013"></a>Criar um caso de teste de roteamento de voz no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-02-07_

<div>

## <a name="to-create-a-test-case"></a>Para criar um caso de teste

1.  Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Roteamento de Voz** e em **Testar Roteamento de Voz**.

4.  Na página **Testar Roteamento de Voz**, clique em **Novo** para criar um novo caso de teste.

5.  Em **Nome**, digite um nome exclusivo para o caso de teste.
    
    O nome deve ser exclusivo entre todos os casos de teste de roteamento de voz em sua implantação do Enterprise Voice. Pode ter até 32 caracteres de comprimento e pode conter qualquer caractere alfanumérico, além da barra invertida (\\), ponto (.) ou sublinhado (\_).

6.  Em **Número discado para fazer um teste**, digite o número discado que deseja usar para testar a configuração de roteamento que você especificar para esse caso de teste. Com base no plano de discagem, na rota e na política de voz, esse número será normalizado e exibido como saída.

7.  Na lista **Plano de Discagem**, selecione o plano de discagem a ser usado ao executar o teste. O padrão é o plano de discagem Global.

8.  Na lista **Política de Voz**, selecione a política de voz a ser usada ao executar o teste. O padrão é a política de voz Global.

9.  Em **Conversão esperada**, digite o número de telefone no formato que você espera ver após a conversão. Esse é o valor do número de telefone que você está testando depois que ele foi convertido pela primeira regra de normalização correspondente no plano de discagem selecionado. Quando você executa o caso de teste, se o número que está testando não resultar no valor em **Conversão esperada**, o teste falhará.

10. (Opcional) Na lista **Uso de PSTN esperado**, você pode selecionar o registro de uso da Rede Telefônica Pública Comutada (PSTN) que espera que seja usado ao executar o caso de teste, com base na política de voz e no plano de discagem especificado. Se um registro de uso diferente do PSTN for usado, o teste falhará.

11. (Opcional) Na lista **Rota esperada**, você pode selecionar a rota de voz que espera que seja usada ao executar o caso de teste, com base na política de voz e no plano de discagem especificado. Se um registro de uso diferente do PSTN for usado, o teste falhará.

12. (Opcional) Clique em **Executar**  para executar o caso de teste. Os resultados são mostrados no painel à direita da página.

13. Clique em **OK**.

14. Clique em **Confirmar** e, em seguida, clique em **Confirmar tudo**.
    
    <div>
    

    > [!NOTE]  
    > Sempre que criar um caso de teste de roteamento de voz, você deve executar o comando <STRONG>Confirmar tudo</STRONG> para publicar a alteração na configuração. Para obter detalhes, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish Pending Changes to The Voice Routing Configuration in Lync Server 2013</A> na documentação operações.

    
    </div>
    
    Se o plano de discagem que está sendo empregado no teste normalizar números de telefone que começam com um sinal de adição (por exemplo, + 12065551219), esse plano pode causar uma falha no teste de roteamento de voz. (O plano de discagem e a rota de voz funcionará; na verdade, o Test-CsDialPlan será bem-sucedido. No entanto, o teste de roteamento de voz pode falhar. É algo que você deve ter em mente ao testar as rotas de voz.

</div>

<div>

## <a name="see-also"></a>Confira também


[Exportar casos de teste de roteamento de voz no Lync Server 2013](lync-server-2013-export-voice-routing-test-cases.md)  
[Importar casos de teste de roteamento de voz no Lync Server 2013](lync-server-2013-import-voice-routing-test-cases.md)  


[Configurando planos de discagem no Lync Server 2013](lync-server-2013-configuring-dial-plans.md)  
[Configurando políticas de voz, registros de uso de PSTN e rotas de voz no Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

