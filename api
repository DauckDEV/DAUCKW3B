const { createClient } = require('@supabase/supabase-js');

const supabase = createClient(
  'https://phdazqdvijgzvsamhxax.supabase.co',
  'YOUR_SERVICE_ROLE_KEY_HERE'
);

module.exports = async (req, res) => {
  const { username, password } = req.body;
  if (!username || !password) return res.status(400).json({ error: 'Missing fields' });

  const { data, error } = await supabase.from('users').insert([{ username, password }]);
  if (error) return res.status(500).json({ error: error.message });

  res.status(200).json({ message: 'Signup success', data });
};
