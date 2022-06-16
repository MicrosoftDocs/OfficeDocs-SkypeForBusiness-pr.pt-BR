No Microsoft Teams, uma conta de recurso é necessária para cada atendedor automático ou fila de chamadas. As contas de recurso também podem receber números de telefone de serviço. É assim que você atribui números de telefone a atendedores automáticos e filas de chamadas, permitindo que os chamadores de fora Teams alcancem o atendedor automático ou a fila de chamadas.

Este artigo aborda como criar contas de recursos e preparar-as para uso com atendedores automáticos e filas de chamadas.

Antes de iniciar os procedimentos neste artigo, verifique se você fez o seguinte:

- [Obter licenças de usuário virtual](#obtain-virtual-user-licenses)
- [Obter números de serviço](#obtain-service-numbers)

> [!NOTE]
> As contas de recursos usadas para atendedores automáticos e filas de chamadas estão desabilitadas para entrar e devem permanecer assim. O chat e a presença não estão disponíveis para essas contas.

### <a name="obtain-virtual-user-licenses"></a>Obter licenças de usuário virtual

Cada conta de recurso requer uma licença para trabalhar com atendedores automáticos e filas de chamadas. Você pode usar uma licença *Telefonia do Microsoft Teams Standard – Usuário Virtual*. Para obter essas licenças, consulte [a licença de Usuário Virtual](../teams-add-on-licensing/virtual-user.md).

Abordaremos como atribuir [a licença a uma conta de recurso posteriormente neste artigo](#assign-a-license).

Se você comprou **Telefonia do Teams Padrão** ou **Teams Telefone** licenças de pacote do Plano de Chamada, as licenças virtuais já estão em sua conta.

Para ver se você já tem licenças virtuais, faça logon Microsoft 365 uma conta com permissões de administrador global. Em seguida, vá para [Cobrança > Seus produtos](https://admin.microsoft.com/Adminportal/Home#/subscriptions). Se você tiver licenças virtuais, elas aparecerão como **Telefonia do Microsoft Teams Padrão – Usuário Virtual**.

1. Abra o Centro de administração do Microsoft 365 e faça logon com um usuário que seja um administrador global. Geralmente, essa é a conta que você usou para se inscrever no Microsoft 365.
2. No painel de navegação esquerdo, vá [ > ](https://admin.microsoft.com/Adminportal/Home#/catalog) >  para **Complementos** >  dos Serviços de Compra de **Cobrança e veja todos os produtos de complementos**.
3. Role até o final para localizar a **licença Telefonia do Microsoft Teams Standard – Usuário Virtual**. Selecione **Detalhes** e, em **seguida, Compre**.
4. Na página de compra de licença, selecione o número de licenças de usuário virtual desejadas. Você precisa de uma licença virtual para cada atendedor automático e fila de chamadas que planeja configurar. É recomendável selecionar pelo menos cinco licenças para que você possa configurar facilmente mais atendedores automáticos e filas de chamadas no futuro sem precisar comprar mais licenças imediatamente.
5. **Desmarque Automaticamente atribuir a todos os usuários sem licenças**.
6. Selecione **Check-out agora**.
7. Confirme seu pedido, selecione **Avançar** e, em seguida, **Fazer pedido**.

Há um custo zero, mas você ainda precisa seguir estas etapas para adquirir a licença.

### <a name="obtain-service-numbers"></a>Obter números de serviço

Os números de serviço são opcionais para atendedores automáticos e filas de chamadas, no entanto, você precisará de pelo menos um número de serviço para que os chamadores acessem o atendedor automático e a configuração da fila de chamadas. Para qualquer atendedor automático ou fila de chamadas que você deseja que seja acessível diretamente por um número de serviço, você deve ter uma conta de recurso com um número de serviço associado.

As contas de recursos podem usar números de serviço de chamada tarifada ou gratuita. Você pode solicitar novos números ou portar números existentes de outra operadora.

Para obter novos números de serviço, consulte [Obter números de telefone de serviço](../getting-service-phone-numbers.md).

Para portar um número de outra operadora, consulte [Transferir números de telefone para Teams](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md).

## <a name="create-a-resource-account"></a>Criar uma conta de recurso

Você pode criar uma conta de recurso no centro Teams administrador.

1. No centro Teams administrador, **expanda Voz** e, em seguida, selecione **Contas de recurso**.
2. Selecione **Adicionar**.
3. No painel **Adicionar conta de recurso** , preencha o **nome de exibição**, o nome de **usuário** e o **tipo de conta de recurso**. O tipo de conta de recurso pode ser **atendedor** automático ou fila de **chamadas,** dependendo de como você pretende usar essa conta de recurso.
4. Selecione **Salvar**.

## <a name="assign-a-license"></a>Atribuir uma licença

Para cada conta de recurso, você deve atribuir uma *licença Telefonia do Microsoft Teams Standard – Usuário Virtual* *ou Telefonia do Teams Padrão* usuário.

1. No Centro de administração do Microsoft 365, expanda **Usuários** e selecione **Usuários ativos**.
2. Selecione a conta de recurso à qual você deseja atribuir uma licença. O painel de usuário da conta de recurso será exibido.
3. Na guia **Licenças e Aplicativos**, em **Licenças**, **selecione Telefonia do Microsoft Teams Padrão – Usuário Virtual**.
4. Selecione **Salvar alterações**.

## <a name="assign-a-service-number"></a>Atribuir um número de serviço

Se você estiver planejando usar a conta de recurso com um atendedor automático ou fila de chamadas que exija um número de serviço, atribua um número à conta de recurso.

1. No centro Teams de administração, na página Contas de recursos, selecione a conta de recurso à qual você deseja atribuir um número de serviço e, em seguida, selecione Atribuir **/cancelar a atribuição**.
2. Na lista **Telefone de tipos de** número, escolha o tipo de número que você deseja usar.
3. Na caixa **Número de telefone Atribuído** , pesquise o número que deseja usar e selecione **Adicionar**. Inclua o código do país (por exemplo, +1 250 555 0012).
4. Selecione **Salvar**.

Para atribuir um roteamento direto ou um número híbrido a uma conta de recurso, você precisa usar o PowerShell:

`Set-CsPhoneNumberAssignment -Identity aa-contoso_main@contoso64.net -PhoneNumber +19295550150 -PhoneNumberType DirectRouting`