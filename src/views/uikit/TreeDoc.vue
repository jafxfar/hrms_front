<template>
    <div class="department-list">
      <div v-for="department in departments" :key="department.name" class="department-card bg-white shadow-sm p-4 rounded-lg">
        <div class="department-header">
          <div>
            <h3 class="department-title">{{ department.name }}</h3>
            <p class="member-count">{{ department.members.length }} Members</p>
          </div>
          <Button label="View All" link class="view-all-btn" />
        </div>
  
        <div class="member-list">
          <div
            v-for="(member, index) in department.members.slice(0, 5)"
            :key="index"
            class="member-item"
          >
            <div class="member-info">
              <Avatar :image="member.avatar" shape="circle" size="large" />
              <div class="member-text">
                <p class="member-name">{{ member.name }}</p>
                <p class="member-role">{{ member.role }}</p>
              </div>
            </div>
            <i class="pi pi-chevron-right member-icon"></i>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>

  const departments = [
    {
      name: 'Design Department',
      members: [
        { name: 'Dianne Russell', role: 'Lead UI/UX Designer', avatar: 'https://i.pravatar.cc/150?img=1' },
        { name: 'Arlene McCoy', role: 'Sr. UI/UX Designer', avatar: 'https://i.pravatar.cc/150?img=2' },
        { name: 'Cody Fisher', role: 'Sr. UI/UX Designer', avatar: 'https://i.pravatar.cc/150?img=3' },
        { name: 'Theresa Webb', role: 'UI/UX Designer', avatar: 'https://i.pravatar.cc/150?img=4' },
        { name: 'Ronald Richards', role: 'UI/UX Designer', avatar: 'https://i.pravatar.cc/150?img=5' },
      ],
    },
    {
      name: 'Sales Department',
      members: [
        { name: 'Darrell Steward', role: 'Sr. Sales Manager', avatar: 'https://i.pravatar.cc/150?img=6' },
        { name: 'Kristin Watson', role: 'Sr. Sales Manager', avatar: 'https://i.pravatar.cc/150?img=7' },
        { name: 'Courtney Henry', role: 'BDM', avatar: 'https://i.pravatar.cc/150?img=8' },
        { name: 'Kathryn Murphy', role: 'BDE', avatar: 'https://i.pravatar.cc/150?img=9' },
        { name: 'Albert Flores', role: 'Sales', avatar: 'https://i.pravatar.cc/150?img=10' },
      ],
    },
    {
      name: 'Project Manager Department',
      members: [
        { name: 'Leslie Alexander', role: 'Sr. Project Manager', avatar: 'https://i.pravatar.cc/150?img=11' },
        { name: 'Ronald Richards', role: 'Sr. Project Manager', avatar: 'https://i.pravatar.cc/150?img=5' },
        { name: 'Savannah Nguyen', role: 'Project Manager', avatar: 'https://i.pravatar.cc/150?img=13' },
        { name: 'Eleanor Pena', role: 'Project Manager', avatar: 'https://i.pravatar.cc/150?img=14' },
        { name: 'Esther Howard', role: 'Project Manager', avatar: 'https://i.pravatar.cc/150?img=15' },
      ],
    },
    {
      name: 'Marketing Department',
      members: [
        { name: 'Wade Warren', role: 'Sr. Marketing Manager', avatar: 'https://i.pravatar.cc/150?img=16' },
        { name: 'Brooklyn Simmons', role: 'Sr. Marketing Manager', avatar: 'https://i.pravatar.cc/150?img=17' },
        { name: 'Kristin Watson', role: 'Marketing Coordinator', avatar: 'https://i.pravatar.cc/150?img=7' },
        { name: 'Jacob Jones', role: 'Marketing Coordinator', avatar: 'https://i.pravatar.cc/150?img=18' },
        { name: 'Cody Fisher', role: 'Marketing', avatar: 'https://i.pravatar.cc/150?img=3' },
      ],
    },
  ];
  </script>
  
  <style scoped>
  .department-list {
    display: flex;
    flex-wrap: wrap;
    gap: 16px;
  }
  
  .department-card {
    flex: 1 1 calc(50% - 16px);
    box-sizing: border-box;
  }
  
  .department-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 12px;
  }
  
  .department-title {
    margin: 0;
    font-size: 18px;
    font-weight: bold;
  }
  
  .member-count {
    margin: 0;
    font-size: 13px;
    color: #666;
  }
  
  .view-all-btn {
    font-size: 14px;
    padding: 0;
    color: #7c3aed;
  }
  
  .member-list {
    display: flex;
    flex-direction: column;
    gap: 12px;
  }
  
  .member-item {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  
  .member-info {
    display: flex;
    align-items: center;
    gap: 12px;
  }
  
  .member-text {
    display: flex;
    flex-direction: column;
  }
  
  .member-name {
    margin: 0;
    font-weight: 500;
  }
  
  .member-role {
    margin: 0;
    font-size: 13px;
    color: #888;
  }
  
  .member-icon {
    font-size: 1vw;
    color: #999;
  }
  </style>
  