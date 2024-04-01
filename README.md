let ownerAddress = 'your address';
let ownerPk = 'your private key';
let ownerPermission = { type: 0, permission_name: 'owner' };
ownerPermission.threshold = 2;
ownerPermission.keys  = [];

let activePermission = { type: 2, permission_name: 'active0' };
activePermission.threshold = 3;
activePermission.operations = '7fff1fc0037e0000000000000000000000000000000000000000000000000000';
activePermission.keys = [];

ownerPermission.keys.push({ address: 'address1', weight: 1 });
ownerPermission.keys.push({ address: 'address2', weight: 1 });
activePermission.keys.push({ address: 'address1', weight: 1 });
activePermission.keys.push({ address: 'address2', weight: 1 });

const updateTransaction = await tronWeb.transactionBuilder.updateAccountPermissions(ownerAddress, ownerPermission, null, [activePermission]);
